---
title: "Получение сведений о компьютере (Visual Basic)"
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
- My.Computer.Info object, tasks
ms.assetid: 13c145bc-5c85-4fea-a5dd-2ca8681a0252
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
ms.openlocfilehash: 8dee43f87a7a09f9b5cd77d5df5c2d0d8c6d4062
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="getting-information-about-the-computer-visual-basic"></a><span data-ttu-id="1c4c4-102">Получение сведений о компьютере (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1c4c4-102">Getting Information about the Computer (Visual Basic)</span></span>
<span data-ttu-id="1c4c4-103">Объект `My.Computer.Info` содержит свойства, которые можно использовать для получения сведений о памяти компьютера, загруженных сборках, имени и операционной системе.</span><span class="sxs-lookup"><span data-stu-id="1c4c4-103">The `My.Computer.Info` object provides properties for getting information about the computer's memory, loaded assemblies, name, and operating system.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1c4c4-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="1c4c4-104">Remarks</span></span>  
 <span data-ttu-id="1c4c4-105">В этой таблице перечислены типичные задачи, выполняемые с помощью объекта `My.Computer.Info`, и указаны разделы, в которых демонстрируется их выполнение.</span><span class="sxs-lookup"><span data-stu-id="1c4c4-105">This table lists tasks commonly accomplished through the `My.Computer.Info` object and points to topics demonstrating how to perform each.</span></span>  
  
|<span data-ttu-id="1c4c4-106">Целевой тип</span><span class="sxs-lookup"><span data-stu-id="1c4c4-106">To</span></span>|<span data-ttu-id="1c4c4-107">См.</span><span class="sxs-lookup"><span data-stu-id="1c4c4-107">See</span></span>|  
|---|---|   
|<span data-ttu-id="1c4c4-108">Определение объема виртуального адресного пространства, доступного на компьютере, на котором установлено приложение</span><span class="sxs-lookup"><span data-stu-id="1c4c4-108">Determine how much virtual address space is available for the computer on which the application is installed</span></span>|<xref:Microsoft.VisualBasic.Devices.ComputerInfo.TotalVirtualMemory%2A>|  
|<span data-ttu-id="1c4c4-109">Определение типа платформы компьютера, на котором выполняется приложение</span><span class="sxs-lookup"><span data-stu-id="1c4c4-109">Determine the platform type of the computer on which the application is running</span></span>|<xref:Microsoft.VisualBasic.Devices.ComputerInfo.OSPlatform%2A>|  
|<span data-ttu-id="1c4c4-110">Определение операционной системы компьютера, на котором выполняется приложение</span><span class="sxs-lookup"><span data-stu-id="1c4c4-110">Determine the operating system of the computer on which the application is running</span></span>|<xref:Microsoft.VisualBasic.Devices.ComputerInfo.OSFullName%2A>|  
|<span data-ttu-id="1c4c4-111">Определение пакетов обновления, установленных на компьютере, на котором выполняется приложение</span><span class="sxs-lookup"><span data-stu-id="1c4c4-111">Determine what service packs have been installed on the computer on which the application is running</span></span>|<xref:Microsoft.VisualBasic.Devices.ComputerInfo.OSVersion%2A>|  
|<span data-ttu-id="1c4c4-112">Определение установленных интерфейсов `UICulture` на компьютере, на котором выполняется приложение.</span><span class="sxs-lookup"><span data-stu-id="1c4c4-112">Determine the installed `UICulture` on the computer on which the application is running.</span></span>|<xref:Microsoft.VisualBasic.Devices.ComputerInfo.InstalledUICulture%2A>|  
  
## <a name="see-also"></a><span data-ttu-id="1c4c4-113">См. также</span><span class="sxs-lookup"><span data-stu-id="1c4c4-113">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Devices.ServerComputer.Info%2A>

