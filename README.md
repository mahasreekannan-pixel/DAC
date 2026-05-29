# DAC
 INTERFACING DAC WITH 8086 KIT AND GENERATING SAWTOOTH AND SQUARE WAVEFORMS

## AIM
To write an assembly language program in 8086 to generate Sawtooth and Square waveforms using DAC.

---

## APPARATUS REQUIRED

| S. No | Item              | Specification   | Quantity |
|-------|------------------|-----------------|----------|
| 1     | Microprocessor kit | 8086            | 1        |
| 2     | Power Supply      | +5 V DC, +12 V DC | 1      |
| 3     | DAC Interface board | -              | 1        |

---

## ALGORITHM

### Measurement of Analog Voltage
1. Send the digital value to DAC.  
2. Read the corresponding analog value at its output.  

### Waveform Generation

#### Square Waveform
1. Send low value (00) to the DAC.  
2. Introduce suitable delay.  
3. Send high value to DAC.  
4. Introduce delay.  
5. Repeat the above procedure.  

#### Sawtooth Waveform
1. Load low value (00) to accumulator.  
2. Send this value to DAC.  
3. Increment the accumulator.  
4. Repeat step (ii) and (iii) until accumulator value reaches FF.  
5. Repeat the above procedure from step 1.  

---

## PROGRAMS

# 8086 Assembly Programs – DAC Interfacing

## Program: Square Wave

| Memory Location | Program     | Comments                          |
|-----------------|-------------|-----------------------------------|
| 1000            | MOV AL,00H  | Load 00H in Accumulator           |
| 1003            |  OUT 0C8H,AL | Send through output port         |
| 1005            |  CALL DELAY(1100)  | CALL PROGRAM TO 1100      |
| 1008            |  MOV AL,0FFH |   Load 00H in Accumulator       |
| 100A            |   OUT 0C8H,AL|  Send through output port       |
| 100D            |  CALL DELAY(1100) | CALL PROGRAM TO 1100       |


| Memory Location | Program     | Comments                          |
|-----------------|-------------|-----------------------------------|
| 1100            | MOV CX,0505  | Load 0505H in Accumulator           |
| 1103            |  DEC CX | Decrement CX        |
| 1105           |  JNZ 1104  | RPEAT UNTILL ZERO      |
| 1108            |   RET |   RETURN TO MAIN PROGRAM      |


# Program: Sawtooth wave

## Assembly Program

| Memory Location | Program Instruction   | Comments                        |
|-----------------|-----------------------|---------------------------------|
| `1000`          | `START: MOV AL,00H`  | Load `00H` in accumulator       |
| `1003`          | `LOOP : OUT 0C8H,AL` | Send through output port        |
| `1005`          | `INC AL`             | Increment contents of accumulator |
| `1007`          | `JNC LOOP`           | Jump if no carry (continue loop) |
| `1009`          | `JMP START`          | Go to starting location         |

---

## Tabulation

| Waveform  | Amplitude | Time period | 
|-----------|-----------|-------------|
| Sawtooth  |   8.08V   |   1.642ms   | 
| Square    |   9.40V   |   6.051ms   |
---

## OUTPUT IMAGE OF DAC(SAWTOOTH WAVE FROM DSO AND SQUARE WAVE FROM DSO)

<img width="1007" height="473" alt="image" src="https://github.com/user-attachments/assets/f17c79f6-8b47-4c6f-b07f-93377027adbc" />

<img width="1007" height="529" alt="image" src="https://github.com/user-attachments/assets/807271ac-481d-431c-8df6-f41b23bbf5ad" />


## Result

Thus, the **DAC was interfaced with 8086** and different **waveforms** were successfully generated.

A variety of other skeletal features are shared by dinosaurs. However, because they either are common to other groups of archosaurs or were not present in all early dinosaurs, these features are not synapomorphies. For example, as diapsids, dinosaurs ancestrally had two pairs of Infratemporal fenestrae (openings in the skull behind the eyes), and as members of the diapsid group Archosauria, had additional openings in the snout and lower jaw.[28] Additionally, several characteristics once thought to be synapomorphies are now known to have appeared before dinosaurs, or were absent in the earliest dinosaurs and independently evolved by different dinosaur groups. These include an elongated scapula, or shoulder blade; a sacrum composed of three or more fused vertebrae (three are found in some other archosaurs, but only two are found in Herrerasaurus);[7] and a perforate acetabulum, or hip socket, with a hole at the center of its inside surface (closed in Saturnalia tupiniquim, for example).[29][30] Another difficulty of determining distinctly dinosaurian features is that early dinosaurs and other archosaurs from the Late Triassic epoch are often poorly known and were similar in many ways; these animals have sometimes been misidentified in the literature.[31]




