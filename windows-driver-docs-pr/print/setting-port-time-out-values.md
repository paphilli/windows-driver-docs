---
title: Setting Port Time-Out Values
description: Setting Port Time-Out Values
keywords:
- port management WDK print , time-out values
- time-outs WDK print
- OpenPort
- SetPortTimeOuts
ms.date: 04/20/2017
---

# Setting Port Time-Out Values





If you are writing a port monitor for a port that has modifiable time-out values, the time-out values should be initialized from within the monitor's [**OpenPort**](/windows-hardware/drivers/ddi/winsplp/nf-winsplp-openport) function. For example the **OpenPort** function in Localmon.dll, the [sample port monitor](sample-port-monitor.md), calls the **SetCommTimeouts** function, described in the Microsoft Windows SDK documentation, for this purpose.

Additionally, a port monitor can optionally provide a [**SetPortTimeOuts**](/previous-versions/ff562630(v=vs.85)) function, which can be called by language monitors. The function is called by Pjlmon.dll, the [sample language monitor](sample-language-monitor.md). The print spooler does not call **SetPortTimeOuts**.

 

