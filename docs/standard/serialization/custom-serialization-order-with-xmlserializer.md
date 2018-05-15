---
title: Порядок пользовательской сериализации с помощью XmlSerializer
ms.date: 03/30/2017
ms.assetid: 975abd20-2a1d-42db-aed3-e898025ccce7
ms.openlocfilehash: 8480644aacf128b430da9881560595bb4b0d3ad5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="custom-serialization-order-with-xmlserializer"></a><span data-ttu-id="9759e-102">Порядок пользовательской сериализации с помощью XmlSerializer</span><span class="sxs-lookup"><span data-stu-id="9759e-102">Custom Serialization Order With XmlSerializer</span></span>
[<span data-ttu-id="9759e-103">Скачать образец</span><span class="sxs-lookup"><span data-stu-id="9759e-103">Download Sample</span></span>](https://download.microsoft.com/download/4/7/B/47B2164C-E780-4B10-8DE4-2CB5B886E0A6/Technologies/Serialization/Xml%20Serialization/CustomOrder.zip.exe)  
  
 <span data-ttu-id="9759e-104">В этом образце показано, как управлять порядком сериализации и десериализации элементов XML-сериализации.</span><span class="sxs-lookup"><span data-stu-id="9759e-104">This sample shows how to control the order of serialized and deserialized elements for XML serialization.</span></span>  
  
 <span data-ttu-id="9759e-105">Дополнительные сведения о сериализации см. в комментариях к исходному коду и в файлах build.proj.</span><span class="sxs-lookup"><span data-stu-id="9759e-105">Review comments in the source code and build.proj files for more information on serialization.</span></span>  
  
### <a name="to-build-the-sample-using-the-command-prompt"></a><span data-ttu-id="9759e-106">Сборка образца с использованием командной строки</span><span class="sxs-lookup"><span data-stu-id="9759e-106">To build the sample using the Command Prompt</span></span>  
  
1.  <span data-ttu-id="9759e-107">Откройте окно командной строки и перейдите к вложенной папке для данного образца, соответствующей выбранному языку.</span><span class="sxs-lookup"><span data-stu-id="9759e-107">Open the Command Prompt window and navigate to one of the language-specific subdirectories for the sample.</span></span>  
  
2.  <span data-ttu-id="9759e-108">В командной строке введите **msbuild CustomOrder.sln**.</span><span class="sxs-lookup"><span data-stu-id="9759e-108">Type **msbuild CustomOrder.sln** at the command line.</span></span>  
  
### <a name="to-build-the-sample-using-visual-studio"></a><span data-ttu-id="9759e-109">Сборка образца с использованием Visual Studio</span><span class="sxs-lookup"><span data-stu-id="9759e-109">To build the sample using Visual Studio</span></span>  
  
1.  <span data-ttu-id="9759e-110">Откройте [!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)] и перейдите к вложенной папке для данного образца, соответствующей выбранному языку.</span><span class="sxs-lookup"><span data-stu-id="9759e-110">Open [!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)] and navigate to one of the language-specific subdirectories for the sample.</span></span>  
  
2.  <span data-ttu-id="9759e-111">Дважды щелкните значок CustomOrder.sln, чтобы открыть файл в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="9759e-111">Double-click the icon for the CustomOrder.sln to open the file in Visual Studio.</span></span>  
  
3.  <span data-ttu-id="9759e-112">В меню **Построение** выберите команду **Построить решение**.</span><span class="sxs-lookup"><span data-stu-id="9759e-112">In the **Build** menu, select **Build Solution**.</span></span>  
  
4.  <span data-ttu-id="9759e-113">По умолчанию сборка образца приложения помещается в подкаталог \bin или \bin\Debug.</span><span class="sxs-lookup"><span data-stu-id="9759e-113">The sample application is built in the default \bin or \bin\Debug subdirectory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9759e-114">См. также</span><span class="sxs-lookup"><span data-stu-id="9759e-114">See Also</span></span>  
 [<span data-ttu-id="9759e-115">Базовая сериализация</span><span class="sxs-lookup"><span data-stu-id="9759e-115">Basic Serialization</span></span>](../../../docs/standard/serialization/basic-serialization.md)  
 [<span data-ttu-id="9759e-116">Двоичная сериализация</span><span class="sxs-lookup"><span data-stu-id="9759e-116">Binary Serialization</span></span>](../../../docs/standard/serialization/binary-serialization.md)  
 [<span data-ttu-id="9759e-117">Управление сериализацией XML с использованием атрибутов</span><span class="sxs-lookup"><span data-stu-id="9759e-117">Controlling XML Serialization Using Attributes</span></span>](../../../docs/standard/serialization/controlling-xml-serialization-using-attributes.md)  
 [<span data-ttu-id="9759e-118">Введение в сериализацию XML</span><span class="sxs-lookup"><span data-stu-id="9759e-118">Introducing XML Serialization</span></span>](../../../docs/standard/serialization/introducing-xml-serialization.md)  
 [<span data-ttu-id="9759e-119">Сериализация</span><span class="sxs-lookup"><span data-stu-id="9759e-119">Serialization</span></span>](../../../docs/standard/serialization/index.md)  
 [<span data-ttu-id="9759e-120">Сериализация XML и SOAP</span><span class="sxs-lookup"><span data-stu-id="9759e-120">XML and SOAP Serialization</span></span>](../../../docs/standard/serialization/xml-and-soap-serialization.md)
