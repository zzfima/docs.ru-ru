---
title: Доступ к ресурсам компьютера (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- computer resources [Visual Basic]
- My.Computer object [Visual Basic], tasks
- computer resources [Visual Basic], accessing
ms.assetid: 75b81c88-f7c0-46e0-95c8-0c006d2120f9
ms.openlocfilehash: 2c53358d483868317887258c92b1aad2d9dcba00
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64662693"
---
# <a name="accessing-computer-resources-visual-basic"></a><span data-ttu-id="64e28-102">Доступ к ресурсам компьютера (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="64e28-102">Accessing computer resources (Visual Basic)</span></span>

<span data-ttu-id="64e28-103">Объект `My.Computer` является одним из трех центральных объектов в `My`, предоставляющих доступ к информации и часто используемым функциям.</span><span class="sxs-lookup"><span data-stu-id="64e28-103">The `My.Computer` object is one of the three central objects in `My`, providing access to information and commonly used functionality.</span></span> <span data-ttu-id="64e28-104">Объект `My.Computer` предоставляет методы, свойства и события для обращения к компьютеру, на котором выполняется приложение.</span><span class="sxs-lookup"><span data-stu-id="64e28-104">`My.Computer` provides methods, properties, and events for accessing the computer on which the application is running.</span></span> <span data-ttu-id="64e28-105">В число его объектов входят следующие:</span><span class="sxs-lookup"><span data-stu-id="64e28-105">Its objects include:</span></span>  
  
- <xref:Microsoft.VisualBasic.Devices.Audio>
- <span data-ttu-id="64e28-106">буфер обмена (<xref:Microsoft.VisualBasic.MyServices.ClipboardProxy>);</span><span class="sxs-lookup"><span data-stu-id="64e28-106">Clipboard (<xref:Microsoft.VisualBasic.MyServices.ClipboardProxy>)</span></span>
- <xref:Microsoft.VisualBasic.Devices.Clock>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem>
- <xref:Microsoft.VisualBasic.Devices.ServerComputer.Info%2A>
- <xref:Microsoft.VisualBasic.Devices.Keyboard>
- <xref:Microsoft.VisualBasic.Devices.Mouse>
- <xref:Microsoft.VisualBasic.Devices.Network>
- <xref:Microsoft.VisualBasic.Devices.Ports>
- <span data-ttu-id="64e28-107">реестр (<xref:Microsoft.VisualBasic.MyServices.RegistryProxy>).</span><span class="sxs-lookup"><span data-stu-id="64e28-107">Registry (<xref:Microsoft.VisualBasic.MyServices.RegistryProxy>)</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="64e28-108">Содержание раздела</span><span class="sxs-lookup"><span data-stu-id="64e28-108">In this section</span></span>

<span data-ttu-id="64e28-109">[Воспроизведение звуков](../../../../visual-basic/developing-apps/programming/computer-resources/playing-sounds.md) </span><span class="sxs-lookup"><span data-stu-id="64e28-109">[Playing Sounds](../../../../visual-basic/developing-apps/programming/computer-resources/playing-sounds.md) </span></span>  
<span data-ttu-id="64e28-110">Перечень задач, связанных с объектом `My.Computer.Audio`, например воспроизведение звука в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="64e28-110">Lists tasks associated with `My.Computer.Audio`, such as playing a sound in the background.</span></span>

<span data-ttu-id="64e28-111">[Сохранение данных в буфер обмена и чтение данных из буфера обмена](../../../../visual-basic/developing-apps/programming/computer-resources/storing-data-to-and-reading-from-the-clipboard.md) </span><span class="sxs-lookup"><span data-stu-id="64e28-111">[Storing Data to and Reading from the Clipboard](../../../../visual-basic/developing-apps/programming/computer-resources/storing-data-to-and-reading-from-the-clipboard.md) </span></span>  
<span data-ttu-id="64e28-112">Перечень задач, связанных с объектом `My.Computer.Clipboard`, например чтение данных из буфера обмена и запись данных в него.</span><span class="sxs-lookup"><span data-stu-id="64e28-112">Lists tasks associated with `My.Computer.Clipboard`, such as reading data from or writing data to the Clipboard.</span></span>

<span data-ttu-id="64e28-113">[Получение сведений о компьютере](../../../../visual-basic/developing-apps/programming/computer-resources/getting-information-about-the-computer.md) </span><span class="sxs-lookup"><span data-stu-id="64e28-113">[Getting Information about the Computer](../../../../visual-basic/developing-apps/programming/computer-resources/getting-information-about-the-computer.md) </span></span>  
<span data-ttu-id="64e28-114">Перечень задач, связанных с объектом `My.Computer.Info`, например определение полного имени компьютера и его IP-адреса.</span><span class="sxs-lookup"><span data-stu-id="64e28-114">Lists tasks associated with `My.Computer.Info`, such as determining a computer's full name or IP addresses.</span></span>

<span data-ttu-id="64e28-115">[Доступ к клавиатуре](../../../../visual-basic/developing-apps/programming/computer-resources/accessing-the-keyboard.md) </span><span class="sxs-lookup"><span data-stu-id="64e28-115">[Accessing the Keyboard](../../../../visual-basic/developing-apps/programming/computer-resources/accessing-the-keyboard.md) </span></span>  
<span data-ttu-id="64e28-116">Перечень задач, связанных с объектом `My.Computer.Keyboard`, например определение того, включен ли режим CAPS LOCK.</span><span class="sxs-lookup"><span data-stu-id="64e28-116">Lists tasks associated with `My.Computer.Keyboard`, such as determining whether CAPS LOCK is on.</span></span>

<span data-ttu-id="64e28-117">[Доступ к мыши](../../../../visual-basic/developing-apps/programming/computer-resources/accessing-the-mouse.md) </span><span class="sxs-lookup"><span data-stu-id="64e28-117">[Accessing the Mouse](../../../../visual-basic/developing-apps/programming/computer-resources/accessing-the-mouse.md) </span></span>  
<span data-ttu-id="64e28-118">Перечень задач, связанных с объектом `My.Computer.Mouse`, например определение факта присутствия мыши.</span><span class="sxs-lookup"><span data-stu-id="64e28-118">Lists tasks associated with `My.Computer.Mouse`, such as determining whether a mouse is present.</span></span>

<span data-ttu-id="64e28-119">[Выполнение сетевых операций](../../../../visual-basic/developing-apps/programming/computer-resources/performing-network-operations.md) </span><span class="sxs-lookup"><span data-stu-id="64e28-119">[Performing Network Operations](../../../../visual-basic/developing-apps/programming/computer-resources/performing-network-operations.md) </span></span>  
<span data-ttu-id="64e28-120">Перечень задач, связанных с объектом `My.Computer.Network`, например отправка и загрузка файлов.</span><span class="sxs-lookup"><span data-stu-id="64e28-120">Lists tasks associated with `My.Computer.Network`, such as uploading or downloading files.</span></span>

<span data-ttu-id="64e28-121">[Доступ к портам компьютера](../../../../visual-basic/developing-apps/programming/computer-resources/accessing-the-computer-s-ports.md) </span><span class="sxs-lookup"><span data-stu-id="64e28-121">[Accessing the Computer's Ports](../../../../visual-basic/developing-apps/programming/computer-resources/accessing-the-computer-s-ports.md) </span></span>  
<span data-ttu-id="64e28-122">Перечень задач, связанных с объектом `My.Computer.Ports`, например отображение доступных последовательных портов и отправка в них строк.</span><span class="sxs-lookup"><span data-stu-id="64e28-122">Lists tasks associated with `My.Computer.Ports`, such as showing available serial ports or sending strings to serial ports.</span></span>

<span data-ttu-id="64e28-123">[Чтение данных из реестра и запись в реестр (Visual Basic)](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md) </span><span class="sxs-lookup"><span data-stu-id="64e28-123">[Reading from and Writing to the Registry](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md) </span></span>  
<span data-ttu-id="64e28-124">Перечень задач, связанных с объектом `My.Computer.Registry`, например чтение данных из реестра и запись данных в него.</span><span class="sxs-lookup"><span data-stu-id="64e28-124">Lists tasks associated with `My.Computer.Registry`, such as reading data from or writing data to registry keys.</span></span>
