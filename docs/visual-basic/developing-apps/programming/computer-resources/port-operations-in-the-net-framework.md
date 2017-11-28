---
title: "Операции с портами в .NET Framework в Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords: ports, Visual Basic
ms.assetid: 1eba223b-7bd3-401a-b097-982bce96df1b
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8db016461ea204eaf349a2c588670a237c9e583b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="port-operations-in-the-net-framework-with-visual-basic"></a><span data-ttu-id="0a5b9-102">Операции с портами в .NET Framework в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0a5b9-102">Port Operations in the .NET Framework with Visual Basic</span></span>
<span data-ttu-id="0a5b9-103">Доступ к последовательным портам компьютера можно получить с помощью классов [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] из пространства имен <xref:System.IO.Ports?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0a5b9-103">You can access your computer's serial ports through the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] classes in the <xref:System.IO.Ports?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="0a5b9-104">Наиболее важный из них, класс <xref:System.IO.Ports.SerialPort>, предоставляет средства для синхронного и управляемого событиями ввода-вывода, для доступа к состоянию подключения-отключения устройства, а также для доступа к свойствам драйвера последовательного порта.</span><span class="sxs-lookup"><span data-stu-id="0a5b9-104">The most important class, <xref:System.IO.Ports.SerialPort>, provides a framework for synchronous and event-driven I/O, access to pin and break states, and access to serial driver properties.</span></span> <span data-ttu-id="0a5b9-105">Он может быть заключен в объект <xref:System.IO.Stream>, доступный через свойство <xref:System.IO.Ports.SerialPort.BaseStream%2A>.</span><span class="sxs-lookup"><span data-stu-id="0a5b9-105">It can be wrapped in a <xref:System.IO.Stream> object, accessible through the <xref:System.IO.Ports.SerialPort.BaseStream%2A> property.</span></span> <span data-ttu-id="0a5b9-106">Упаковка <xref:System.IO.Ports.SerialPort> в объект <xref:System.IO.Stream> предоставляет доступ к последовательному порту для классов, использующих потоки.</span><span class="sxs-lookup"><span data-stu-id="0a5b9-106">Wrapping <xref:System.IO.Ports.SerialPort> in a <xref:System.IO.Stream> object allows the serial port to be accessed by classes that use streams.</span></span> <span data-ttu-id="0a5b9-107">Пространство имен включает перечисления, которые упрощают управление последовательными портами.</span><span class="sxs-lookup"><span data-stu-id="0a5b9-107">The namespace includes enumerations that simplify the control of serial ports.</span></span>  
  
 <span data-ttu-id="0a5b9-108">Самый простой способ создать объект <xref:System.IO.Ports.SerialPort> — это метод <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.</span><span class="sxs-lookup"><span data-stu-id="0a5b9-108">The simplest way to create a <xref:System.IO.Ports.SerialPort> object is through the <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A> method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0a5b9-109">Классы [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] нельзя использовать для прямого доступа к другим типам портов, таким как параллельные порты, USB-порты и т. д.</span><span class="sxs-lookup"><span data-stu-id="0a5b9-109">You cannot use [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] classes to directly access other types of ports, such as parallel ports, USB ports, and so on.</span></span>  
  
## <a name="enumerations"></a><span data-ttu-id="0a5b9-110">Перечисления</span><span class="sxs-lookup"><span data-stu-id="0a5b9-110">Enumerations</span></span>  
 <span data-ttu-id="0a5b9-111">В этой таблице указаны и описаны основные перечисления, которые используются для доступа к последовательному порту:</span><span class="sxs-lookup"><span data-stu-id="0a5b9-111">This table lists and describes the main enumerations used for accessing a serial port:</span></span>  
  
|<span data-ttu-id="0a5b9-112">Перечисление</span><span class="sxs-lookup"><span data-stu-id="0a5b9-112">Enumeration</span></span>|<span data-ttu-id="0a5b9-113">Описание</span><span class="sxs-lookup"><span data-stu-id="0a5b9-113">Description</span></span>|  
|---|---|   
|<xref:System.IO.Ports.Handshake>|<span data-ttu-id="0a5b9-114">Определяет протокол управления, который организует связь с последовательным портом для объекта <xref:System.IO.Ports.SerialPort>.</span><span class="sxs-lookup"><span data-stu-id="0a5b9-114">Specifies the control protocol used in establishing a serial port communication for a <xref:System.IO.Ports.SerialPort> object.</span></span>|  
|<xref:System.IO.Ports.Parity>|<span data-ttu-id="0a5b9-115">Задает бит четности для объекта <xref:System.IO.Ports.SerialPort>.</span><span class="sxs-lookup"><span data-stu-id="0a5b9-115">Specifies the parity bit for a <xref:System.IO.Ports.SerialPort> object.</span></span>|  
|<xref:System.IO.Ports.SerialData>|<span data-ttu-id="0a5b9-116">Указывает тип символа, полученного от последовательного порта в объект <xref:System.IO.Ports.SerialPort>.</span><span class="sxs-lookup"><span data-stu-id="0a5b9-116">Specifies the type of character that was received on the serial port of the <xref:System.IO.Ports.SerialPort> object.</span></span>|  
|<xref:System.IO.Ports.SerialError>|<span data-ttu-id="0a5b9-117">Указывает ошибки, возникшие в объекте <xref:System.IO.Ports.SerialPort>.</span><span class="sxs-lookup"><span data-stu-id="0a5b9-117">Specifies errors that occur on the <xref:System.IO.Ports.SerialPort> object</span></span>|  
|<xref:System.IO.Ports.SerialPinChange>|<span data-ttu-id="0a5b9-118">Указывает тип изменения, произошедшего с объектом <xref:System.IO.Ports.SerialPort>.</span><span class="sxs-lookup"><span data-stu-id="0a5b9-118">Specifies the type of change that occurred on the <xref:System.IO.Ports.SerialPort> object.</span></span>|  
|<xref:System.IO.Ports.StopBits>|<span data-ttu-id="0a5b9-119">Указывает число стоповых битов, используемых для объекта <xref:System.IO.Ports.SerialPort>.</span><span class="sxs-lookup"><span data-stu-id="0a5b9-119">Specifies the number of stop bits used on the <xref:System.IO.Ports.SerialPort> object.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0a5b9-120">См. также</span><span class="sxs-lookup"><span data-stu-id="0a5b9-120">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Devices.Ports>  
 [<span data-ttu-id="0a5b9-121">Доступ к портам компьютера</span><span class="sxs-lookup"><span data-stu-id="0a5b9-121">Accessing the Computer's Ports</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/accessing-the-computer-s-ports.md)
