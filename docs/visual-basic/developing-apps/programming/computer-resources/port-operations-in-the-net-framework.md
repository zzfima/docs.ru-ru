---
title: Операции с портами в .NET Framework
ms.date: 07/20/2015
helpviewer_keywords:
- ports, Visual Basic
ms.assetid: 1eba223b-7bd3-401a-b097-982bce96df1b
ms.openlocfilehash: 68f0c67b8135c6bb7ce8a134e2a324bc12c0aad9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "74345502"
---
# <a name="port-operations-in-the-net-framework-with-visual-basic"></a>Операции с портами в .NET Framework в Visual Basic

Доступ к последовательным портам компьютера можно получить с помощью классов .NET Framework из пространства имен <xref:System.IO.Ports?displayProperty=nameWithType>. Наиболее важный из них, класс <xref:System.IO.Ports.SerialPort>, предоставляет средства для синхронного и управляемого событиями ввода-вывода, для доступа к состоянию подключения-отключения устройства, а также для доступа к свойствам драйвера последовательного порта. Он может быть заключен в объект <xref:System.IO.Stream>, доступный через свойство <xref:System.IO.Ports.SerialPort.BaseStream>. Упаковка <xref:System.IO.Ports.SerialPort> в объект <xref:System.IO.Stream> предоставляет доступ к последовательному порту для классов, использующих потоки. Пространство имен включает перечисления, которые упрощают управление последовательными портами.

Самый простой способ создать объект <xref:System.IO.Ports.SerialPort> — это метод <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.

> [!NOTE]
> Классы .NET Framework нельзя использовать для прямого доступа к другим типам портов, таким как параллельные порты, USB-порты и т. д.

## <a name="enumerations"></a>Перечисления

В этой таблице указаны и описаны основные перечисления, которые используются для доступа к последовательному порту:

|Перечисление|Описание:|
|---|---|
|<xref:System.IO.Ports.Handshake>|Определяет протокол управления, который организует связь с последовательным портом для объекта <xref:System.IO.Ports.SerialPort>.|
|<xref:System.IO.Ports.Parity>|Задает бит четности для объекта <xref:System.IO.Ports.SerialPort>.|
|<xref:System.IO.Ports.SerialData>|Указывает тип символа, полученного от последовательного порта в объект <xref:System.IO.Ports.SerialPort>.|
|<xref:System.IO.Ports.SerialError>|Указывает ошибки, возникшие в объекте <xref:System.IO.Ports.SerialPort>.|
|<xref:System.IO.Ports.SerialPinChange>|Указывает тип изменения, произошедшего с объектом <xref:System.IO.Ports.SerialPort>.|
|<xref:System.IO.Ports.StopBits>|Указывает число стоповых битов, используемых для объекта <xref:System.IO.Ports.SerialPort>.|

## <a name="see-also"></a>См. также раздел

- <xref:Microsoft.VisualBasic.Devices.Ports>
- [Доступ к портам компьютера](../../../../visual-basic/developing-apps/programming/computer-resources/accessing-the-computer-s-ports.md)
