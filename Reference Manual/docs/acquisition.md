# How is data acquired?

## How is data retrieved?

- Conversion software requires two scripts (segno CLI executable and configuration yaml). Each segno.exe and ctu_config.yml is named based on their version for corresponding firmware and supported operating systems.  
- The ReadMe document linked below defines which supported system, known issues, and troubleshooting.  
    - (Link?)  
- The software is located in *RADC_Device_Group/ANNE/Parsers and Analysis Code/Parsers*.  
    - The files needed are the executable in the *Windows Sibel SHRD Processor v0.3.5* or *MacOS.Sibel.SHRD.Processor.v0.3.5* folder and *cfg.yml*.  
- The RADC data is compressed into .tar.gz format. To untar the folders on Windows to access the .shrd files use the following command:  
```
tar -xvzf 'C:\PATH\FILE.tar.gz'
```
- To convert the .shrd files into usable .csv and .edf files, use the following command:  
```
"segno_cli-x86_64-windows-0.3.5.exe" -c "chest.shrd" -l "limb.shrd" -o "output.directory" -n "prefix" -cfg "cfg.yml"
```

## What are the device outputs?

### Chest

<details> 
<summary>prefix_accl_gyro_raw.csv</summary>

Specs:  
- Fs: 210 Hz  
- Headings: Time(ms), Velocity X(dps), Velocity Y(dps), Velocity Z(dps), Accl X(g), Accl Y(g), Accl Z(g)  
</details>

<details> 
<summary>prefix_ecg_raw.csv</summary>

Specs:  
- Fs: 512 Hz  
- Headings: Time(ms), ECG Amplitude(mV), ADC   
</details>

<details> 
<summary>prefix_chest_temp_raw.csv</summary>

Specs:  
- Fs: 0.25 Hz  
- Headings: Time(ms), Chest Temp(Celsius)  
</details>
<br> 

### Limb

<details> 
<summary>prefix_ppg_raw.csv</summary>

Specs:  
- Fs: 129 Hz  
- Headings: Time(ms), Red(nA), IR(nA)  
</details>

<details> 
<summary>prefix_limb_temp_raw.csv</summary>

Specs:  
- Fs: 0.25 Hz  
- Headings: Time(ms), Limb Temp(Celsius)  
</details>
<br> 

### Summary Files

<details> 
<summary>prefix_vitals.csv</summary>

Specs:  
- Fs: 1 Hz  
- Headings: Time(ms), HR(bpm), ECG SQI, SpO2(%), PI(%), PR(bpm), PPG SQI, RR(rpm), RR SQI, RR Channel, Accl X(g), Accl Y(g), Accl Z(g), PAT(ms), Chest Temp(Celsius), Limb Temp(Celsius)  
</details>

<br> <br>