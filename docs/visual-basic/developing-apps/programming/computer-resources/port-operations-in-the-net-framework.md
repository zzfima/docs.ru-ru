---
title: "Операции с портами в .NET Framework в Visual Basic"
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: e01853cba19ffa0a7d9997eef3d25d2b2e3166dd
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="port-operations-in-the-net-framework-with-visual-basic"></a>Операции с портами в .NET Framework в Visual Basic
Доступ к последовательным портам компьютера можно получить с помощью классов [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] из пространства имен <xref:System.IO.Ports?displayProperty=fullName>. Наиболее важный из них, класс <xref:System.IO.Ports.SerialPort>, предоставляет средства для синхронного и управляемого событиями ввода-вывода, для доступа к состоянию подключения-отключения устройства, а также для доступа к свойствам драйвера последовательного порта. Он может быть заключен в объект <xref:System.IO.Stream>, доступный через свойство <xref:System.IO.Ports.SerialPort.BaseStream%2A>. Упаковка <xref:System.IO.Ports.SerialPort> в объект <xref:System.IO.Stream> предоставляет доступ к последовательному порту для классов, использующих потоки. Пространство имен включает перечисления, которые упрощают управление последовательными портами.  
  
 Самый простой способ создать объект <xref:System.IO.Ports.SerialPort> — это метод <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.  
  
> [!NOTE]
>  Классы [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] нельзя использовать для прямого доступа к другим типам портов, таким как параллельные порты, USB-порты и т. д.  
  
## <a name="enumerations"></a>Перечисления  
 В этой таблице указаны и описаны основные перечисления, которые используются для доступа к последовательному порту:  
  
|Перечисление|Описание|  
|---|---|   
|<xref:System.IO.Ports.Handshake>|Определяет протокол управления, который организует связь с последовательным портом для объекта <xref:System.IO.Ports.SerialPort>.|  
|<xref:System.IO.Ports.Parity>|Задает бит четности для объекта <xref:System.IO.Ports.SerialPort>.|  
|<xref:System.IO.Ports.SerialData>|Указывает тип символа, полученного от последовательного порта в объект <xref:System.IO.Ports.SerialPort>.|  
|<xref:System.IO.Ports.SerialError>|Указывает ошибки, возникшие в объекте <xref:System.IO.Ports.SerialPort>.|  
|<xref:System.IO.Ports.SerialPinChange>|Указывает тип изменения, произошедшего с объектом <xref:System.IO.Ports.SerialPort>.|  
|<xref:System.IO.Ports.StopBits>|Указывает число стоповых битов, используемых для объекта <xref:System.IO.Ports.SerialPort>.|  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.Devices.Ports>   
 [Доступ к портам компьютера](../../../../visual-basic/developing-apps/programming/computer-resources/accessing-the-computer-s-ports.md)

