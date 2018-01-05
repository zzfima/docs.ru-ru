---
title: "Порядок пользовательской сериализации с помощью XmlSerializer"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 975abd20-2a1d-42db-aed3-e898025ccce7
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: ae5969060938763fee63c514de0a87eadbe6537a
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="custom-serialization-order-with-xmlserializer"></a><span data-ttu-id="7b3ae-102">Порядок пользовательской сериализации с помощью XmlSerializer</span><span class="sxs-lookup"><span data-stu-id="7b3ae-102">Custom Serialization Order With XmlSerializer</span></span>
[<span data-ttu-id="7b3ae-103">Скачать образец</span><span class="sxs-lookup"><span data-stu-id="7b3ae-103">Download Sample</span></span>](http://download.microsoft.com/download/4/7/B/47B2164C-E780-4B10-8DE4-2CB5B886E0A6/Technologies/Serialization/Xml%20Serialization/CustomOrder.zip.exe)  
  
 <span data-ttu-id="7b3ae-104">В этом образце показано, как управлять порядком сериализации и десериализации элементов XML-сериализации.</span><span class="sxs-lookup"><span data-stu-id="7b3ae-104">This sample shows how to control the order of serialized and deserialized elements for XML serialization.</span></span>  
  
 <span data-ttu-id="7b3ae-105">Дополнительные сведения о сериализации см. в комментариях к исходному коду и в файлах build.proj.</span><span class="sxs-lookup"><span data-stu-id="7b3ae-105">Review comments in the source code and build.proj files for more information on serialization.</span></span>  
  
### <a name="to-build-the-sample-using-the-command-prompt"></a><span data-ttu-id="7b3ae-106">Сборка образца с использованием командной строки</span><span class="sxs-lookup"><span data-stu-id="7b3ae-106">To build the sample using the Command Prompt</span></span>  
  
1.  <span data-ttu-id="7b3ae-107">Откройте окно командной строки и перейдите к вложенной папке для данного образца, соответствующей выбранному языку.</span><span class="sxs-lookup"><span data-stu-id="7b3ae-107">Open the Command Prompt window and navigate to one of the language-specific subdirectories for the sample.</span></span>  
  
2.  <span data-ttu-id="7b3ae-108">В командной строке введите **msbuild CustomOrder.sln**.</span><span class="sxs-lookup"><span data-stu-id="7b3ae-108">Type **msbuild CustomOrder.sln** at the command line.</span></span>  
  
### <a name="to-build-the-sample-using-visual-studio"></a><span data-ttu-id="7b3ae-109">Сборка образца с использованием Visual Studio</span><span class="sxs-lookup"><span data-stu-id="7b3ae-109">To build the sample using Visual Studio</span></span>  
  
1.  <span data-ttu-id="7b3ae-110">Откройте [!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)] и перейдите к вложенной папке для данного образца, соответствующей выбранному языку.</span><span class="sxs-lookup"><span data-stu-id="7b3ae-110">Open [!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)] and navigate to one of the language-specific subdirectories for the sample.</span></span>  
  
2.  <span data-ttu-id="7b3ae-111">Дважды щелкните значок CustomOrder.sln, чтобы открыть файл в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="7b3ae-111">Double-click the icon for the CustomOrder.sln to open the file in Visual Studio.</span></span>  
  
3.  <span data-ttu-id="7b3ae-112">В меню **Построение** выберите команду **Построить решение**.</span><span class="sxs-lookup"><span data-stu-id="7b3ae-112">In the **Build** menu, select **Build Solution**.</span></span>  
  
4.  <span data-ttu-id="7b3ae-113">По умолчанию сборка образца приложения помещается в подкаталог \bin или \bin\Debug.</span><span class="sxs-lookup"><span data-stu-id="7b3ae-113">The sample application is built in the default \bin or \bin\Debug subdirectory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b3ae-114">См. также</span><span class="sxs-lookup"><span data-stu-id="7b3ae-114">See Also</span></span>  
 [<span data-ttu-id="7b3ae-115">Базовая сериализация</span><span class="sxs-lookup"><span data-stu-id="7b3ae-115">Basic Serialization</span></span>](../../../docs/standard/serialization/basic-serialization.md)  
 [<span data-ttu-id="7b3ae-116">Двоичная сериализация</span><span class="sxs-lookup"><span data-stu-id="7b3ae-116">Binary Serialization</span></span>](../../../docs/standard/serialization/binary-serialization.md)  
 [<span data-ttu-id="7b3ae-117">Управление сериализацией XML с использованием атрибутов</span><span class="sxs-lookup"><span data-stu-id="7b3ae-117">Controlling XML Serialization Using Attributes</span></span>](../../../docs/standard/serialization/controlling-xml-serialization-using-attributes.md)  
 [<span data-ttu-id="7b3ae-118">Введение в сериализацию XML</span><span class="sxs-lookup"><span data-stu-id="7b3ae-118">Introducing XML Serialization</span></span>](../../../docs/standard/serialization/introducing-xml-serialization.md)  
 [<span data-ttu-id="7b3ae-119">Сериализация</span><span class="sxs-lookup"><span data-stu-id="7b3ae-119">Serialization</span></span>](../../../docs/standard/serialization/index.md)  
 [<span data-ttu-id="7b3ae-120">Сериализация XML и SOAP</span><span class="sxs-lookup"><span data-stu-id="7b3ae-120">XML and SOAP Serialization</span></span>](../../../docs/standard/serialization/xml-and-soap-serialization.md)
