# Step7
STL

Task for automation
- The scope of work includes the development of a PLC control program, its testing and debugging
- The existing plant automation system is implemented on Siemens SIMATIC S7-300 controller: 6ES7318-3EL01-0AB0 – CPU 319-3 PN/DP
- Used field device connector - SIMATIC DP/PA FDC 157-0: 6ES7157-0AC83-0XA0
- Recommended field communication interface - Profibus PA
- Develop an additional visualization page for the new fuel phase preparation system.
- Place the fuel phase preparation control page on the central operator console and on the CP6 control panel.
- The fill level of the container must be permanently displayed on this page.
- The fuel phase can be prepared in automatic and manual modes
- Automatic mode assumes sequential dosing of components into the B-FS-09 container according to the selected recipe.
- Provide for the possibility of programming the recipe on the operator's page (on the central operator console and on the CP6 control panel).
- Provide for the possibility of storing up to 20 recipes in memory. The following parameters must be specified in the recipe:
    - Recipe name
    - Total weight of the batch (kg)
    - Component loading sequences
    - Amount (kg) or volume (% of total weight) of mineral oil
    - Quantity (kg) or volume ((% of total weight)) of emulsifier 1
    - Amount (kg) or volume ((% of total weight)) of emulsifier 2
    - Mixing time (min)
    - Whether a stirrer is used during cooking or not (yes/no)

- Fuel phase preparation sequence:
    - The current balance in the tank B-FS-09 is checked. If there is a balance above a certain minimum (which can be configured), the system should give an error - "merge the previous batch"
    - Recipe Selection
    - "Start cooking in automatic mode"
    - The system checks which pump P-FS-03 or P-FS-04 is currently free. If any is free, the system switches the corresponding valve H-FS-49 or H-FS-50 to the position for supplying oil to the B-FS-09 tank, the pump turns on and works until the required level in the tank is reached. The mass of the pumped oil is controlled by a tensometric system on the tank.
    - When starting to load the components, the agitator is switched on
    - After the oil is loaded, the system switches the H-FS-51 valve to position 1, turns on the P-FS-10 pump and starts pumping emulsifier 1. The mass of the pumped emulsifier is controlled by the tensometric system on the tank.
    - After the emulsifier 1 is loaded, the system switches the H-FS-51 valve to position 2, turns on the P-FS-10 pump and starts pumping the emulsifier 2. The mass of the pumped emulsifier is controlled by a tensometric system on the tank.
    - After the completion of the injection of all components and the stage of mixing the FF, the operator controls the quality of the resulting TF and if the results are satisfactory, presses the button "TF is ready", the message "Preparation of the fuel phase is completed" is displayed on the operator's screen. Before pressing the “TF is ready” button, the operator has the opportunity to add any of the components to the B-FS-09 tank in the required quantity.
    - Prior to pressing the FF Ready button, the operator must not be able to pump FF from the B-FS-09 tank.
    - After pressing the FF Ready button, the operator should not be able to add ingredients to the B-FS-09 preparation tank.
    - It should be possible to turn off the TF Ready status from the TF preparation page.
    - After the preparation of the fuel phase is completed, it can either be used in the current process or transferred to a special IBC for further storage. To do this, provide a button - "download fuel phase in IBC". In this case, the H-FS-52 valve switches to the IBC position (B-FS-10) and the P-FS-02 pump is turned on.
    - In the event of a process interruption for any reason, there must be it is possible to continue the preparation of the fuel phase from the interrupted moment.



− Sequence of fuel phase preparation:
o The current balance in the tank B-FS-09 is checked. If there is a remainder
above some minimum (which can be adjusted), the system should
give an error - "merge the previous batch"
o Recipe Selection
o "Start cooking in automatic mode"
o The system checks which pump P-FS-03 or P-FS-04 is currently free. If any is free, the system switches 
corresponding valve H-FS-49 or H-FS-50 to supply position 
oil into the container B-FS-09, the pump turns on and runs until it reaches
required level in the tank. The mass of pumped oil is controlled
strain gauge system on the tank.
o When starting to load the components, the agitator is switched on
o After the oil loading is completed, the system switches the H-FS-51 valve to
position 1, turns on the P-FS-10 pump and starts pumping emulsifier 1.
The mass of the pumped emulsifier is controlled by tensometric
container system.
o After loading emulsifier 1, the system switches the H-FS 51 valve to position 2, turns on the P-FS-10 pump and starts pumping the emulsifier
2. The mass of the pumped emulsifier is controlled by a tensometric
container system.
o After the completion of the injection of all components and the stage of mixing the FF,
the operator controls the quality of the received TF and, when satisfactory results, presses the "TF ready" button, the screen
operator, the message “Preparation of the fuel phase
completed." Before pressing the "TF ready" button, the operator has the opportunity
add any of the components to the container B-FS-09 in the required
quantity.
o Before pressing the “TF ready” button, the operator should not be able to
pump TF from the tank B-FS-09.
o After pressing the “TF ready” button, the operator should not be able to
add ingredients to the B-FS-09 preparation container.
o It should be possible to disable the "TF Ready" status from the page
TF preparation.
o After the preparation of the fuel phase is completed, it can either be
used in the current process, or pumped into a special IBC for
further storage. To do this, provide a button - "download
fuel phase in IBC". In this case, the H-FS-52 valve switches to
position on the IBC (B-FS-10) and the pump P-FS-02 is turned on
o In the event of a process interruption for any reason, there must be
it is possible to continue the preparation of the fuel phase with
interrupted moment.
− Manual mode involves sequential dosing of components into a container
B-FS-09 operator selectable via dialog box
