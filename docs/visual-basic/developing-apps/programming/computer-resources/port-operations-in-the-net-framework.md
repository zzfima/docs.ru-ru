---
title: "Операции с портами в .NET Framework в Visual Basic | Документы Майкрософт"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- ports, Visual Basic
ms.assetid: 1eba223b-7bd3-401a-b097-982bce96df1b
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 61b91fe5f3bb016bace838b9eeabb1a59190bfe9
ms.lasthandoff: 03/13/2017

---
# <a name="port-operations-in-the-net-framework-with-visual-basic"></a>Операции с портами в .NET Framework в Visual Basic
Доступ к последовательным портам компьютера можно получить с помощью классов [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] в пространстве имен <xref:System.IO.Ports?displayProperty=fullName>. Наиболее важный класс, <xref:System.IO.Ports.SerialPort>, предоставляет средства для синхронного и управляемого событиями ввода-вывода, доступа к состоянию подключения-отключения устройства, а также доступа к свойствам драйвера последовательного порта. Он может быть вложен в объект <xref:System.IO.Stream>, доступный через свойство <xref:System.IO.Ports.SerialPort.BaseStream%2A>. Вложение класса <xref:System.IO.Ports.SerialPort> в объект <xref:System.IO.Stream> обеспечивает доступ к этому последовательному порту для классов, использующих потоки. Пространство имен включает перечисления, которые упрощают управление последовательными портами.  
  
 Проще всего создать объект <xref:System.IO.Ports.SerialPort> с помощью метода <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.  
  
> [!NOTE]
>  Классы [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] нельзя использовать для прямого доступа к другим типам портов, таким как параллельные порты, USB-порты и т. д.  
  
## <a name="enumerations"></a>Перечисления  
 В этой таблице указаны и описаны основные перечисления, которые используются для доступа к последовательному порту:  
  
|Перечисление|Описание|  
|---|---|   
|<xref:System.IO.Ports.Handshake>|Определяет протокол управления, которые используется для связи с объектом <xref:System.IO.Ports.SerialPort> через последовательный порт.|  
|<xref:System.IO.Ports.Parity>|Задает бит четности для объекта <xref:System.IO.Ports.SerialPort>.|  
|<xref:System.IO.Ports.SerialData>|Указывает тип символа, полученный на последовательный порт объекта <xref:System.IO.Ports.SerialPort>.|  
|<xref:System.IO.Ports.SerialError>|Указывает ошибки, возникающие в объекте <xref:System.IO.Ports.SerialPort>.|  
|<xref:System.IO.Ports.SerialPinChange>|Указывает тип изменений, произведенных на объекте <xref:System.IO.Ports.SerialPort>.|  
|<xref:System.IO.Ports.StopBits>|Указывает число стоповых битов, используемых в объекте <xref:System.IO.Ports.SerialPort>.|  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.Devices.Ports>   
 [Доступ к портам компьютера](../../../../visual-basic/developing-apps/programming/computer-resources/accessing-the-computer-s-ports.md)
