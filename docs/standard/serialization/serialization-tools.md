---
title: "Инструменты сериализации"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 593b675f-938c-44ff-807b-0ca9fea30103
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: cf1ad835d6fcebee6a048c0f7059eac8af15a89f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="serialization-tools"></a><span data-ttu-id="1ff34-102">Инструменты сериализации</span><span class="sxs-lookup"><span data-stu-id="1ff34-102">Serialization Tools</span></span>
<span data-ttu-id="1ff34-103">Данный раздел содержит подробные сведения об инструментах сериализации.</span><span class="sxs-lookup"><span data-stu-id="1ff34-103">This section contains detailed information about the serialization tools.</span></span> <span data-ttu-id="1ff34-104">Все инструменты можно запускать из командной строки.</span><span class="sxs-lookup"><span data-stu-id="1ff34-104">You can run all the tools from the command line.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="1ff34-105">Для нормальной работы инструментов .NET Framework необходимо правильно настроить переменные среды Path, Include и Lib.</span><span class="sxs-lookup"><span data-stu-id="1ff34-105">For the .NET Framework tools to function properly, you must set your Path, Include, and Lib environment variables correctly.</span></span> <span data-ttu-id="1ff34-106">Эти переменные устанавливаются с помощью программы SDKVars.bat, расположенной в каталоге \<SDK>\v2.0\Bin.</span><span class="sxs-lookup"><span data-stu-id="1ff34-106">Set these environment variables by running SDKVars.bat, which is located in the \<SDK>\v2.0\Bin directory.</span></span> <span data-ttu-id="1ff34-107">Программу SDKVars.bat следует выполнять в каждой командной оболочке.</span><span class="sxs-lookup"><span data-stu-id="1ff34-107">SDKVars.bat must be executed in every command shell.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1ff34-108">Содержание</span><span class="sxs-lookup"><span data-stu-id="1ff34-108">In This Section</span></span>  
  
|<span data-ttu-id="1ff34-109">Средство</span><span class="sxs-lookup"><span data-stu-id="1ff34-109">Tool</span></span>|<span data-ttu-id="1ff34-110">Описание</span><span class="sxs-lookup"><span data-stu-id="1ff34-110">Description</span></span>|  
|----------|-----------------|  
|[<span data-ttu-id="1ff34-111">Инструмент создания XML-сериализатора (Sgen.exe)</span><span class="sxs-lookup"><span data-stu-id="1ff34-111">XML Serializer Generator Tool (Sgen.exe)</span></span>](../../../docs/standard/serialization/xml-serializer-generator-tool-sgen-exe.md)|<span data-ttu-id="1ff34-112">Создает сборку XML-сериализации для типов в указанной сборке для повышения быстродействия <xref:System.Xml.Serialization.XmlSerializer> во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="1ff34-112">Creates an XML serialization assembly for types in a specified assembly in order to improve the run-time performance of the <xref:System.Xml.Serialization.XmlSerializer>.</span></span>|  
|[<span data-ttu-id="1ff34-113">Инструмент определения схемы XML (Xsd.exe)</span><span class="sxs-lookup"><span data-stu-id="1ff34-113">XML Schema Definition Tool (Xsd.exe)</span></span>](../../../docs/standard/serialization/xml-schema-definition-tool-xsd-exe.md)|<span data-ttu-id="1ff34-114">Создает схемы XML на языке XSD, предложенном консорциумом World Wide Web Consortium (W3C).</span><span class="sxs-lookup"><span data-stu-id="1ff34-114">Generates XML schemas that follow the XSD language proposed by the World Wide Web Consortium (W3C).</span></span> <span data-ttu-id="1ff34-115">Этот инструмент генерирует классы CLR и классы <xref:System.Data.DataSet> на основе XSD-файла схемы.</span><span class="sxs-lookup"><span data-stu-id="1ff34-115">This tool generates common language runtime classes and <xref:System.Data.DataSet> classes from an XSD schema file.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1ff34-116">См. также</span><span class="sxs-lookup"><span data-stu-id="1ff34-116">See Also</span></span>  
 [<span data-ttu-id="1ff34-117">Инструменты</span><span class="sxs-lookup"><span data-stu-id="1ff34-117">Tools</span></span>](../../../docs/framework/tools/index.md)
