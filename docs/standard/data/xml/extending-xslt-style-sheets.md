---
title: Расширение таблиц стилей XSLT
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: df4ba2bf-a99e-4d22-bbf3-04fc67669dbc
ms.openlocfilehash: 04f9788fe34ba74d0cf12fdd37adf46e85777192
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710873"
---
# <a name="extending-xslt-style-sheets"></a><span data-ttu-id="b16e3-102">Расширение таблиц стилей XSLT</span><span class="sxs-lookup"><span data-stu-id="b16e3-102">Extending XSLT Style Sheets</span></span>
<span data-ttu-id="b16e3-103">В этом разделе описаны различные методы расширения функциональных возможностей XSLT.</span><span class="sxs-lookup"><span data-stu-id="b16e3-103">This section describes the different methods of extending the XSLT functionality.</span></span> <span data-ttu-id="b16e3-104">С помощью класса <xref:System.Xml.Xsl.XsltArgumentList> можно добавлять объекты расширения или параметры.</span><span class="sxs-lookup"><span data-stu-id="b16e3-104">You can add extension objects or parameters using the <xref:System.Xml.Xsl.XsltArgumentList> class.</span></span> <span data-ttu-id="b16e3-105">Затем объекты расширения или параметры можно вызывать из таблицы стилей.</span><span class="sxs-lookup"><span data-stu-id="b16e3-105">The extension objects or parameters can then be called from the style sheet.</span></span> <span data-ttu-id="b16e3-106">Кроме того, можно внедрять в таблицу стилей блоки скрипта с помощью элемента `msxsl:script`.</span><span class="sxs-lookup"><span data-stu-id="b16e3-106">In addition, you can also embed script blocks into the style sheet by using the `msxsl:script` element.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b16e3-107">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="b16e3-107">In This Section</span></span>  
 [<span data-ttu-id="b16e3-108">Объекты расширения XSLT</span><span class="sxs-lookup"><span data-stu-id="b16e3-108">XSLT Extension Objects</span></span>](../../../../docs/standard/data/xml/xslt-extension-objects.md)  
 <span data-ttu-id="b16e3-109">Обсуждается использование класса <xref:System.Xml.Xsl.XsltArgumentList> для обработки объектов расширения XSLT.</span><span class="sxs-lookup"><span data-stu-id="b16e3-109">Discusses using the <xref:System.Xml.Xsl.XsltArgumentList> class to process XSLT extension objects.</span></span>  
  
 [<span data-ttu-id="b16e3-110">Параметры XSLT</span><span class="sxs-lookup"><span data-stu-id="b16e3-110">XSLT Parameters</span></span>](../../../../docs/standard/data/xml/xslt-parameters.md)  
 <span data-ttu-id="b16e3-111">Обсуждается использование класса <xref:System.Xml.Xsl.XsltArgumentList> для обработки параметров XSLT.</span><span class="sxs-lookup"><span data-stu-id="b16e3-111">Discusses using the <xref:System.Xml.Xsl.XsltArgumentList> class to process XSLT parameters.</span></span>  
  
 [<span data-ttu-id="b16e3-112">Блоки скриптов с использованием msxsl:script</span><span class="sxs-lookup"><span data-stu-id="b16e3-112">Script Blocks Using msxsl:script</span></span>](../../../../docs/standard/data/xml/script-blocks-using-msxsl-script.md)  
 <span data-ttu-id="b16e3-113">Обсуждается использование элемента `msxsl:script`.</span><span class="sxs-lookup"><span data-stu-id="b16e3-113">Discusses using the `msxsl:script` element.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="b16e3-114">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="b16e3-114">Related Sections</span></span>  
 [<span data-ttu-id="b16e3-115">Преобразования XSLT</span><span class="sxs-lookup"><span data-stu-id="b16e3-115">XSLT Transformations</span></span>](../../../../docs/standard/data/xml/xslt-transformations.md)
