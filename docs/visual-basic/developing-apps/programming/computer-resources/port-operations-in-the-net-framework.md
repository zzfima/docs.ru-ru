---
title: "Операции с портами в .NET Framework в Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "порты, Visual Basic"
ms.assetid: 1eba223b-7bd3-401a-b097-982bce96df1b
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# Операции с портами в .NET Framework в Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Доступ к последовательным портам компьютера можно получить с помощью классов [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort-md.md)] в пространстве имен <xref:System.IO.Ports?displayProperty=fullName>.  Наиболее важный класс <xref:System.IO.Ports.SerialPort> предоставляет средства для синхронного и управляемого событиями ввода\-вывода, доступа к состоянию подключения\-отключения устройства, а также для доступа к свойствам драйвера последовательного порта.  Он может быть заключен в оболочку объекта <xref:System.IO.Stream>, доступного через свойство <xref:System.IO.Ports.SerialPort.BaseStream%2A>.  Заключение объекта <xref:System.IO.Ports.SerialPort> в оболочку объекта <xref:System.IO.Stream> позволяет обеспечить доступ к последовательному порту с помощью классов, использующих потоки.  Пространство имен включает перечисления, которые упрощают управление последовательными портами.  
  
 Самым простым способом создания объекта <xref:System.IO.Ports.SerialPort> является использование метода <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.  
  
> [!NOTE]
>  Нельзя использовать классы [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort-md.md)] для непосредственного доступа к портам других типов, например параллельным портам, USB\-портам и т. д.  
  
## Перечисления  
 В этой таблице приведен список и описания основных перечислений, используемые для доступа к последовательному порту.  
  
|||  
|-|-|  
|Перечисление|Описание|  
|<xref:System.IO.Ports.Handshake>|Определяет протокол управления, используемый для установления связи через последовательный порт для объекта <xref:System.IO.Ports.SerialPort>.|  
|<xref:System.IO.Ports.Parity>|Задает бит четности для объекта <xref:System.IO.Ports.SerialPort>.|  
|<xref:System.IO.Ports.SerialData>|Указывает тип символа, полученного в последовательном порту объекта <xref:System.IO.Ports.SerialPort>.|  
|<xref:System.IO.Ports.SerialError>|Указывает ошибки, возникающие в объекте <xref:System.IO.Ports.SerialPort>|  
|<xref:System.IO.Ports.SerialPinChange>|Указывает тип изменения, произошедшего в объекте <xref:System.IO.Ports.SerialPort>.|  
|<xref:System.IO.Ports.StopBits>|Указывает число стоповых битов, используемых в объекте <xref:System.IO.Ports.SerialPort>.|  
  
## См. также  
 <xref:Microsoft.VisualBasic.Devices.Ports>   
 [Доступ к портам компьютера](../../../../visual-basic/developing-apps/programming/computer-resources/accessing-the-computer-s-ports.md)