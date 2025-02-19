This setup demonstrates programming the MachXO5’s SRAM using Slave SPI (SSPI) with an STM32F411 Discovery board.

Since the MachXO5 bitstream is too large for the microcontroller’s internal flash, it is stored in an external SPI flash. This setup utilizes two SPI buses: one for reading the bitstream from SPI flash and another for programming the MachXO5.
![image](https://github.com/user-attachments/assets/96256ca6-1206-4ed2-9e29-a7228259b173)

The instructions used in this program follows the instruction from FPGA-TN-02271-2.1([MachXO5 Programming and Configuration User Guide](https://www.latticesemi.com/view_document?document_id=53489))

Key considerations for the Slave SPI (SSPI) configuration:

1.Ensure that INITN is high before sending the Slave SPI activation key. This can be achieved by monitoring INITN or introducing a delay after pulling PROGRAMN low before transmitting the activation key.

2. Read the status registers before and after sending the bitstream to verify that the DONE bit is correctly set and that no configuration errors have occurred.

The programming flow used in this example is applicable to all Lattice Nexus FPGA family devices.

Main.c follows the procedure indicated in FPGA-TN-02271-2.1:

![XO5_Image_4](https://github.com/user-attachments/assets/4e186a2a-a7c4-4ded-bd8f-4edf0f633da7)

![image](https://github.com/user-attachments/assets/0f3d564f-a0f6-4837-820e-dce6124c24da)


