<script lang="ts">
  import summary from '#lib/data/report-4471-summary.json';

  const total = summary.causes.reduce((n, cause) => n + cause.reports, 0);
  const repeatedRows = summary.sourceRows - summary.uniqueReports;
</script>

<p class="sum">
  <strong>{summary.uniqueReports}</strong> unique reports from {summary.sourceRows} export rows ·
  <strong>{summary.causes.length}</strong> distinct causes · {repeatedRows} repeated rows removed
</p>

<table>
  <thead>
    <tr><th>cause</th><th>reports</th><th>channel</th><th>intake tags</th><th>tenants</th><th>seen</th></tr>
  </thead>
  <tbody>
    {#each summary.causes as cause (cause.id)}
      <tr>
        <td><code>{cause.id}</code></td>
        <td>{cause.reports}</td>
        <td>{Object.entries(cause.channels).map(([channel, count]) => `${channel} ×${count}`).join(' · ')}</td>
        <td>{Object.entries(cause.intakeTags).map(([tag, count]) => `${tag} ×${count}`).join(' · ')}</td>
        <td>{cause.tenants}</td>
        <td>{cause.firstSeen} → {cause.lastSeen}</td>
      </tr>
    {/each}
  </tbody>
</table>

<p class="note">The {summary.causes[0].oneDayMoveNotes} one-day-move notes belong to the parser cause. Intake tags are guesses; they do not determine the cause.</p>
<p class="sum">Check: {total} reports across all causes.</p>

<style>
  .sum { font-size: 1.05rem; }
  .note { color: var(--muted, #6b6a66); font-size: 0.9rem; }
  table { border-collapse: collapse; width: 100%; margin: 1rem 0; font-size: 0.92rem; }
  th, td { border-bottom: 1px solid var(--line, #e3e0d8); padding: 0.45rem 0.5rem; text-align: left; vertical-align: top; }
  code { font-family: ui-monospace, Menlo, monospace; }
</style>
