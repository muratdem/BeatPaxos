# BeatPaxos

Interactive single-page Paxos consensus tutorial game. Players try (and fail) to break the safety invariant by killing and delaying nodes.

## Structure

Single file app: `index.html` — all HTML, CSS, and JS inline. Deployed on GitHub Pages.

## Paxos Implementation

- Single-decree Paxos with 3 nodes (Red, Green, Blue)
- Messages: p1a (prepare), p1b (promise), p2a (accept), p2b (accepted), p3 (decide)
- Ballot numbering: Red uses 1,4,7..., Green uses 2,5,8..., Blue uses 3,6,9...
- Message colors in lanes and animations follow the ballot owner (leader), not the sender

## Game Mechanics

- Double-click: kill/recover a node (only one down at a time)
- Click & hold: delay a node's message processing
- Score: max(0, messages_sent - 5) per round; first 5 are "free" (normal Paxos)
- Timeouts (30-54s) trigger new proposals when leader is unresponsive
- After consensus, new round auto-starts

## Timing (at 1x speed)

- Message travel: 5000ms
- Process delay: 1500ms
- Leader timeout: 30000-54000ms
- Round end delay: 6000ms
