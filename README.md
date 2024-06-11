## Introduction:
The Reliable Transport Protocol addresses the challenge of ensuring data transfer reliability over an unreliable network. This protocol offers a reliable channel for data transfer, handling issues such as packet loss, corruption, and out-of-order packets. Two primary protocols studied are Go-Back-N and Selective Repeat, with the project focusing on implementing the Go-Back-N protocol.

## Project Description:
The project aims to implement a transport protocol enhancing UDP's reliability through the Go-Back-N protocol. It involves creating specialized GBN sender and receiver scripts, each with distinct functionalities.

## Sender:
- **Functionality:** Divides the file into chunks and transmits them over UDP using the Go-Back-N protocol.
- **Arguments:** Requires filename, receiver IP address, and receiver port as input.
- **Steps:**
  1. Divides the file into segments.
  2. Transmits segments and waits for acknowledgments.
  3. Responds to acknowledgment events (ACK) and timeout events.

## Receiver:
- **Functionality:** Receives packets, stores data, and sends acknowledgments.
- **Steps:**
  - Upon packet reception:
    - Parses received packet.
    - Stores application data if the packet ID matches the expected ID.
    - Sends acknowledgment with the ID of the last correctly received packet.
  - Upon receiving the last packet:
    - Writes data to a new file.
    - Sends acknowledgment.
    - Indicates file reception completion.

## Simulated Loss:
To simulate network conditions, random packet loss (5%-15%) is introduced by randomly dropping received packets at the receiver.

<p align="center">
<img src="https://github.com/Bosy-Ayman/Go-Back-N/assets/112729185/3f418446-c433-470b-a704-f3104af5fa2d" alt="Simulated Loss" width="700">
</p>
