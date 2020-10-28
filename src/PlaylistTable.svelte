<script>
export let name;
export let author;
export let tracks = [];
export let skipHeaderRow;
export let additionalProps = [];

function getArtistStringFromTrack(track) {
  var artistString = '';
  if (Array.isArray(track.artists) && track.artists.length > 0) {
    var artistNames = track.artists.map(a => a.name);
    if (artistNames.length === 1) {
      artistString = artistNames[0];
    }
    else if (artistNames.length === 2) {
      artistString = artistNames[0] + ' and ' + artistNames[1];
    }
    else {
      artistString = artistNames.slice(0, -1).join(', ') + ', and ' + artistNames.slice(-1);
    }
  }
  return artistString;
}
</script>
<section class="playlist-container">

<h2>{name}</h2>
<div>by {author}</div>

<table class="playlist-root">
{#if !skipHeaderRow}
  <thead>
    <th>Song</th>
    <th>Artist</th>
    {#each additionalProps as prop}
      {prop.displayName}
    {/each}
  </thead>
{/if}
  <tbody>
    {#each tracks as track}
    <tr class="track">
      <td class="cell song">
        <a href={track.uri}>{track.name}</a>
      </td>
      <td class="cell artist">
        {getArtistStringFromTrack(track)}
      </td>
      {#each additionalProps as prop}
        <td class="cell {prop.name}">
          {track[prop.name]}
        </td>
      {/each}
    </tr>
    {/each}
  </tbody>
</table>
</section>

<style>

.playlist-container {
  font-family: circular, Helvetica Neue, Ubuntu, sans-serif;
}

.playlist-root {
  background-color: #181818;
  border-collapse: collapse;
  border-radius: 4px;
  color: #fff;
}

.playlist-root th {
  text-align: left;
  text-transform: uppercase;
  font-size: 11px;
  letter-spacing: 0.16em;
  font-weight: 200;
  color: #A0A0A0;
  line-height: 28px;
  text-transform: uppercase;
  vertical-align: bottom;
  padding-left: 10px;
}

.cell {
  text-align: left;
  border-top: 1px solid #282828;
  padding-top: 6px;
  padding-bottom: 6px;
  padding-left: 10px;
}

.playlist-root a:link {
  color: #fff;
  text-decoration: none;
  font-size: 1em;
  letter-spacing: 0.015em;
  font-weight: 200;
}

</style>
