@startuml
start

:IGenerateReportFileLogic Interface;
if (Method Call?) then (MeterConfigurationReport)
    :Input: ConnectedDeviceInfo, FilePath, Culture;
    :Process: Generate a meter configuration report;
    :Output: Report file saved at FilePath;
elseif (MeterComparisonReport)
    :Input: ConnectedDeviceInfo, UploadedFilePath, DownloadFilePath, ShowIdentical, Culture;
    :Process: Compare meter data and generate a comparison report;
    :Output: Comparison report saved at DownloadFilePath;
elseif (ExportModbusRegisters)
    :Input: Device, FilePath, Culture;
    :Process: Export Modbus registers to a file;
    :Output: Modbus register file saved at FilePath;
else
    :Invalid Method Call;
endif

stop
@enduml
