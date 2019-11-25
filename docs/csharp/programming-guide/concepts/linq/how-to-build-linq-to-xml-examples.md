---
title: Практическое руководство. Сборка примеров LINQ to XML (C#)
ms.date: 07/20/2015
ms.assetid: e5d18fa1-2704-48fe-a44b-1564f97c9e9c
ms.openlocfilehash: 289a13daed7e3c871156bf50c6fa04c113c0cd13
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/16/2019
ms.locfileid: "74141457"
---
# <a name="how-to-build-linq-to-xml-examples-c"></a><span data-ttu-id="00832-102">Практическое руководство. Сборка примеров LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="00832-102">How to build LINQ to XML examples (C#)</span></span>
<span data-ttu-id="00832-103">В разных фрагментах кода и примерах, приведенных в этой документации, используются классы и типы из различных пространств имен.</span><span class="sxs-lookup"><span data-stu-id="00832-103">The various snippets and examples in this documentation use classes and types from a variety of namespaces.</span></span> <span data-ttu-id="00832-104">При компиляции кода C# необходимо указывать соответствующие директивы `using`.</span><span class="sxs-lookup"><span data-stu-id="00832-104">When compiling C# code, you need to supply appropriate `using` directives.</span></span>  
  
## <a name="example"></a><span data-ttu-id="00832-105">Пример</span><span class="sxs-lookup"><span data-stu-id="00832-105">Example</span></span>  
 <span data-ttu-id="00832-106">Следующий код содержит директивы `using`, которые требуются для построения и запуска примеров на C#.</span><span class="sxs-lookup"><span data-stu-id="00832-106">The following code contains the `using` directives that the C# examples require to build and run.</span></span> <span data-ttu-id="00832-107">Не все директивы `using` требуются для каждого примера.</span><span class="sxs-lookup"><span data-stu-id="00832-107">Not all `using` directives are required for every example.</span></span>  
  
```csharp  
using System;  
using System.Diagnostics;  
using System.Collections;  
using System.Collections.Generic;  
using System.Collections.Specialized;  
using System.Text;  
using System.Linq;  
using System.Xml;  
using System.Xml.Linq;  
using System.Xml.Schema;  
using System.Xml.XPath;  
using System.Xml.Xsl;  
using System.IO;  
using System.Threading;  
using System.Reflection;  
using System.IO.Packaging;  
```  
  
## <a name="see-also"></a><span data-ttu-id="00832-108">См. также</span><span class="sxs-lookup"><span data-stu-id="00832-108">See also</span></span>

- [<span data-ttu-id="00832-109">Общие сведения о программировании LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="00832-109">LINQ to XML Programming Overview (C#)</span></span>](./linq-to-xml-overview.md)
