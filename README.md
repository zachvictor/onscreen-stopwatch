# Onscreen Stopwatch

A stopwatch for screen recordings. The page shows the time and nothing else.

<p>
  <img src="docs/dark.png" width="340" alt="The dark theme, with the stopwatch running">
  <img src="docs/light.png" width="340" alt="The light theme, with the stopwatch stopped">
</p>

## Why

A screen recording often has a long wait in the middle of a task. You cut the wait, and then the viewer cannot tell how long the task took.

Keep this stopwatch in the frame. After the cut, the time jumps, and the viewer sees how long the task took.

## Use

Open the [hosted page](https://zachvictor.github.io/onscreen-stopwatch/).

To use the stopwatch offline, download `index.html` and open it in a browser. The page is one file. It needs no server and no build step.

| Action           | Mouse          | Key   |
|------------------|----------------|-------|
| Start or stop    | Click the time | Space |
| Reset            | Reset button   | R     |
| Float            | Float button   | F     |
| Switch the theme | Theme button   | T     |

- The time scales to fill the window, so the window can be small.
- The buttons appear after the pointer rests on the window for a moment. A quick click on the time does not show them.
- The keys work only while the stopwatch window has focus.
- The color of the time shows the state:

  | State   | Dark theme | Light theme |
  |---------|------------|-------------|
  | At zero | Grey       | Grey        |
  | Running | White      | Black       |
  | Stopped | Yellow     | Orange      |

- The dark theme is the default. The browser remembers the theme that you select.

## Float

Float moves the stopwatch into a small window that stays on top of other windows. Close that window to return the stopwatch to the tab.

Float uses the [Document Picture-in-Picture API](https://developer.mozilla.org/en-US/docs/Web/API/Document_Picture-in-Picture_API). Chrome and Edge support this API. The Float button does not appear in a browser that does not support it.

## Accuracy

The stopwatch reads the monotonic clock of the browser (`performance.now()`). It does not count ticks, so a hidden or throttled window does not lose time.

The display shows tenths of a second. It truncates the time and does not round it.

## Tested

Chrome 158 on macOS.

## License

[MIT](LICENSE)
