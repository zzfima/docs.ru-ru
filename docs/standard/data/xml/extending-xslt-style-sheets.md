---
title: "Расширение таблиц стилей XSLT"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: df4ba2bf-a99e-4d22-bbf3-04fc67669dbc
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: aea28532dd81745b8d018cbeed454bbd008c8ed7
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="extending-xslt-style-sheets"></a><span data-ttu-id="a440b-102">Расширение таблиц стилей XSLT</span><span class="sxs-lookup"><span data-stu-id="a440b-102">Extending XSLT Style Sheets</span></span>
<span data-ttu-id="a440b-103">В этом разделе описаны различные методы расширения функциональных возможностей XSLT.</span><span class="sxs-lookup"><span data-stu-id="a440b-103">This section describes the different methods of extending the XSLT functionality.</span></span> <span data-ttu-id="a440b-104">С помощью класса <xref:System.Xml.Xsl.XsltArgumentList> можно добавлять объекты расширения или параметры.</span><span class="sxs-lookup"><span data-stu-id="a440b-104">You can add extension objects or parameters using the <xref:System.Xml.Xsl.XsltArgumentList> class.</span></span> <span data-ttu-id="a440b-105">Затем объекты расширения или параметры можно вызывать из таблицы стилей.</span><span class="sxs-lookup"><span data-stu-id="a440b-105">The extension objects or parameters can then be called from the style sheet.</span></span> <span data-ttu-id="a440b-106">Кроме того, можно внедрять в таблицу стилей блоки скрипта с помощью элемента `msxsl:script`.</span><span class="sxs-lookup"><span data-stu-id="a440b-106">In addition, you can also embed script blocks into the style sheet by using the `msxsl:script` element.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a440b-107">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="a440b-107">In This Section</span></span>  
 [<span data-ttu-id="a440b-108">Объекты расширения XSLT</span><span class="sxs-lookup"><span data-stu-id="a440b-108">XSLT Extension Objects</span></span>](../../../../docs/standard/data/xml/xslt-extension-objects.md)  
 <span data-ttu-id="a440b-109">Обсуждается использование класса <xref:System.Xml.Xsl.XsltArgumentList> для обработки объектов расширения XSLT.</span><span class="sxs-lookup"><span data-stu-id="a440b-109">Discusses using the <xref:System.Xml.Xsl.XsltArgumentList> class to process XSLT extension objects.</span></span>  
  
 [<span data-ttu-id="a440b-110">Параметры XSLT</span><span class="sxs-lookup"><span data-stu-id="a440b-110">XSLT Parameters</span></span>](../../../../docs/standard/data/xml/xslt-parameters.md)  
 <span data-ttu-id="a440b-111">Обсуждается использование класса <xref:System.Xml.Xsl.XsltArgumentList> для обработки параметров XSLT.</span><span class="sxs-lookup"><span data-stu-id="a440b-111">Discusses using the <xref:System.Xml.Xsl.XsltArgumentList> class to process XSLT parameters.</span></span>  
  
 [<span data-ttu-id="a440b-112">Блоки скриптов с использованием msxsl:script</span><span class="sxs-lookup"><span data-stu-id="a440b-112">Script Blocks Using msxsl:script</span></span>](../../../../docs/standard/data/xml/script-blocks-using-msxsl-script.md)  
 <span data-ttu-id="a440b-113">Обсуждается использование элемента `msxsl:script`.</span><span class="sxs-lookup"><span data-stu-id="a440b-113">Discusses using the `msxsl:script` element.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="a440b-114">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="a440b-114">Related Sections</span></span>  
 [<span data-ttu-id="a440b-115">Преобразования XSLT</span><span class="sxs-lookup"><span data-stu-id="a440b-115">XSLT Transformations</span></span>](../../../../docs/standard/data/xml/xslt-transformations.md)
