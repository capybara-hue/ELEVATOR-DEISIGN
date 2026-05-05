# RTL Innovate Hackfest: Smart Elevator Controller[cite: 2]

This repository contains the Verilog implementation of a 3-floor elevator controller designed by Team **VTX (Verilog Vortex)**.

# Design Approach
The system is built using a **Moore Finite State Machine (FSM)** to ensure stable, clock-synchronized transitions between floors.

*   **States**: The design defines three primary states: S0 (Floor 0), S1 (Floor 1), and S2 (Floor 2).
*   **Request Handling**: When the input `x` is high, the system advances to the next floor (Up Counter behavior).
*   **Direction Control**: At the top floor (S2), a high input `x` triggers a transition back to the starting floor (Down Counter behavior).
*   **Idle Logic**: A high reset (`rst`) signal immediately places the elevator into an IDLE state at Floor 0.

# Technical Specifications
*   **RTL Language**: Verilog.
*   **Hardware Logic**: Uses non-blocking assignments (`<=`) for sequential state memory and combinational logic for next-state decoding.
*   **Safety**: Includes a `default` state case to prevent the controller from entering undefined or "stuck" logic states.
*   **Tools**: Designed and verified using **Cadence SimVision** for schematic tracing and waveform analysis.

# Verification
The provided testbench (`vtxc_tb.v`) simulates the system heartbeat via a clock and validates the following:
1.  **Reset Recovery**: Confirms the system returns to S0 upon reset.
2.  **State Sequence**: Verifies the $S0 \rightarrow S1 \rightarrow S2$ transition path.
3.  **Output Accuracy**: Ensures the output signal `y` triggers only when the designated floor is reached.

#  Team VTX
*   **Ananya Chaturvedi**
*   **Srishti Prajapati**
