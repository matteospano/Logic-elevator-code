# Elevator Logic Lab

**A small, interactive laboratory for learning how programs make decisions.** Build an elevator controller by connecting events, conditions, and actions in a visual rule editor, then run a simulated rush hour and observe the consequences in real time.

> Instead of writing unrestricted code, you program with a deliberately limited set of building blocks. The interface makes the rules easy to inspect, while the simulation makes their behavior tangible.

## Why this project?

Elevator Logic Lab explores a simple idea: programming can be taught and tested through a constrained, visual language. A user edits controller logic from a front-end interface, runs the same controlled environment, and sees how those choices affect a measurable outcome.

The elevator is one example of a broader pattern that can be used for other approachable simulations—especially systems with a small number of understandable variables, events, and actions. Examples might include traffic lights, warehouse robots, or a basic production line.

## How it works

The workbench represents each instruction as an ordered rule:

**When an event occurs → if a condition is true → perform an action using a parameter**

For example:

> When an up-button is pressed → if this is the closest available elevator → go to the calling floor.

Rules are evaluated from top to bottom. More than one matching rule may run for an event, so both rule order and the selected event, condition, action, and parameter can change the controller's behavior. Add, remove, reorder, or edit rules in the workbench, then run the simulation to test your changes.

### Available building blocks

- **Events:** On Start, On Idle, On Up Button Pressed, On Down Button Pressed, On Floor Button Pressed, On Passing Floor, and On Stopping At Floor.
- **Conditions:** Always, Elevator is empty, Elevator has passengers, Closest available elevator, Moving up, and Moving down.
- **Actions:** Go to floor, Queue floor, Open doors, Close doors, and Stop.
- **Parameters:** Context-aware choices such as Calling floor, Passenger destination, Next destination, Closest hall call, Current floor, adjacent floors, and a specific floor.

Parameters connect an action to values from the simulation. For instance, **Queue floor ← Passenger destination** uses the destination selected by a passenger when boarding.

### Starter controller

The default rules provide a working starting point:

1. Dispatch the closest available elevator to a new up or down hall call.
2. Queue a passenger's selected destination when they board.
3. When idle, head to the next destination or nearest waiting call.
4. Open the doors when arriving at a target floor.

Restore the starter logic at any time and experiment by changing one rule at a time.

## Run an experiment

1. Open `index.html` in a modern browser. No installation, build step, or server is required.
2. Choose the number of elevators and floors.
3. Edit, add, remove, or reorder controller rules.
4. Select **Run simulation** and watch passenger calls and elevator behavior in the live building view.
5. Compare the results, return to **Edit logic**, and try another controller.

Each test runs for **60 simulated seconds**. Calls are generated automatically, and the same general setup makes it easy to compare different rule strategies. Passenger generation is randomized, so individual runs can vary; for a fair comparison, run each strategy more than once.

The simulation reports passengers delivered, time remaining, delivery rate, average passenger wait, and elevator moves. The event feed and waiting queue provide context for interpreting those results—not just the final score.

## Project structure

- `index.html` — the complete application: interface, styles, rule editor, and simulation logic.
- `script.js` and `style.css` — currently empty placeholders; the working implementation is self-contained in `index.html`.

## Implementation notes

The editable rules are data, not JavaScript entered by the user. The app interprets those choices through a small event/condition/action system. This keeps the learning interface approachable and limits programs to operations the simulation understands.

The elevator model includes configurable floor and elevator counts, passenger calls and destinations, elevator capacity, travel and door timing, pickup and delivery, and live status reporting. It is intentionally compact: a useful sandbox for exploring cause and effect, not a model of real-world elevator safety or dispatch systems.

Live demo: https://codepen.io/editor/matteospano/pen/01a13fe4-ab0f-7a4b-9beb-9976912a146f

## Ideas for extending the lab

The same approach can support other simple simulations while keeping the rule language and model manageable:

- Define a small set of variables and events that learners can understand.
- Expose only safe, meaningful actions through the editor.
- Keep the simulation state visible so users can connect a rule to its effect.
- Add clear metrics that help compare strategies.
- Preserve repeatable settings—or add seeded randomness—to make experiments easier to evaluate.

## License

No license is currently specified. Add a license before reusing or distributing this project under particular terms.
