# Robot Battle

Arduino-based sumo/battle robot for a university robotics competition. The robot uses sonar for target detection, IR sensors for edge (floor) detection, and DC motors with a dual H-bridge driver for movement.

## Hardware

| Component | Role |
|---|---|
| Arduino Mega | Main controller |
| HC-SR04 ultrasonic sonar (x2) | Target / wall detection |
| TCRT5000 / GP2Y0A21 IR sensors | Floor edge detection (prevent falling off arena) |
| MDD10A dual motor driver | DC motor H-bridge control |
| DC motors (x2 or x4) | Differential / mecanum drive |

## How It Works

1. **Startup**: IR sensors auto-calibrate by sampling ambient readings for a threshold baseline.
2. **Scanning**: Robot sweeps using sonar to locate the opponent.
3. **Attack**: Drives toward the detected target at variable speed based on distance.
4. **Edge avoidance**: IR sensors continuously check for the arena edge; the robot reverses and turns if the floor disappears.

## Directory Structure

| Directory | Description |
|---|---|
| `main/` | Final competition firmware — integrated sonar + IR + movement |
| `PID_control/` | PID-controlled movement experiments (includes MPU test) |
| `mechanum/` | Mecanum wheel drive code (pin layout reference) |
| `movement testing/` | Incremental dev tests — `move.ino`, `scan.ino`, `dis_hold.ino`, `Fall_testing.ino` |
| `Sonar testing/` | HC-SR04 test code with test result spreadsheets |
| `IR testing/` | TCRT5000 and GP2Y0A21 IR sensor test code |
| `ref/` | Datasheets — HC-SR04, MDD10A, GP2Y0A21, TCRT5000 |

## Branches

| Branch | Description |
|---|---|
| `master` | Current main code |
| `2023` | 2023 competition version |
| `2024` | 2024 competition version |
| `wu_code` | Teammate's code branch |
| `gpt-test` | GPT-assisted experiment |
