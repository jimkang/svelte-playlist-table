# svelte-playlist-table

A thing to put in your Svelte app to render lists of track objects as a playlist.

## Installation

    npm install svelte-playlist-table

## Usage

    <script>
    import PlaylistTable from 'svelte-playlist-table';

    let error;
    </script>

    <div>
      <PlaylistTable tracks={tracks} name={playlist.name} author={playlist.owner.display_name} />
    </div>

![Example render](meta/example-render.png)

- `name`
- `author`
- `tracks`: An array of objects with `uri`, `name`, and `artists` properties.
- `skipHeaderRow`: Set true to not render a header row.
- `additionalProps`: Additional props to render in the table. An array of objects each having a `name` and `displayName` property. The `name` must correspond to a property on the track objects.

## License

The MIT License (MIT)

Copyright (c) 2020 Jim Kang

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the 'Software'), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED 'AS IS', WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
