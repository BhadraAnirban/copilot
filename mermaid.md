graph TD
    A[IGenerateReportFileLogic Interface] -->|Method Call| B{Select Method}
    B -->|MeterConfigurationReport| C[Input: ConnectedDeviceInfo, FilePath, Culture]
    C --> D[Process: Generate a meter configuration report]
    D --> E[Output: Report file saved at FilePath]
    B -->|MeterComparisonReport| F[Input: ConnectedDeviceInfo, UploadedFilePath, DownloadFilePath, ShowIdentical, Culture]
    F --> G[Process: Compare meter data and generate a comparison report]
    G --> H[Output: Comparison report saved at DownloadFilePath]
    B -->|ExportModbusRegisters| I[Input: Device, FilePath, Culture]
    I --> J[Process: Export Modbus registers to a file]
    J --> K[Output: Modbus register file saved at FilePath]
    B -->|Invalid Method Call| L[Error: Invalid method selected]