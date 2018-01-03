---
title: "Была создана ссылка на внедренную сборку взаимодействия &#39; &lt;assembly1&gt;&#39; из-за наличия неявной ссылки на эту сборку из сборки &#39;&lt; Assembly2&gt;&#39;"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc40059
- bc40059
helpviewer_keywords:
- VBC40059
- BC40059
ms.assetid: 520e39cb-8ab6-46f5-aa00-08afd51b4b7c
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: aaaa7460ade00ad4232807ce11ee125e270742bf
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="a-reference-was-created-to-embedded-interop-assembly-39ltassembly1gt39-because-of-an-indirect-reference-to-that-assembly-from-assembly-39ltassembly2gt39"></a><span data-ttu-id="cdae4-102">Была создана ссылка на внедренную сборку взаимодействия &#39; &lt;assembly1&gt;&#39; из-за наличия неявной ссылки на эту сборку из сборки &#39;&lt; Assembly2&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="cdae4-102">A reference was created to embedded interop assembly &#39;&lt;assembly1&gt;&#39; because of an indirect reference to that assembly from assembly &#39;&lt;assembly2&gt;&#39;</span></span>
<span data-ttu-id="cdae4-103">Была создана ссылка на внедренную сборку взаимодействия "\<сборка1>" из-за косвенной ссылки на эту сборку из сборки "\<сборка2>".</span><span class="sxs-lookup"><span data-stu-id="cdae4-103">A reference was created to embedded interop assembly '\<assembly1>' because of an indirect reference to that assembly from assembly '\<assembly2>'.</span></span> <span data-ttu-id="cdae4-104">Рекомендуется изменить свойство "Внедрить типы взаимодействия" в одной из сборок.</span><span class="sxs-lookup"><span data-stu-id="cdae4-104">Consider changing the 'Embed Interop Types' property on either assembly.</span></span>  
  
 <span data-ttu-id="cdae4-105">Была добавлена ссылка на сборку (сборка1), для которой свойству `Embed Interop Types` присвоено значение `True`.</span><span class="sxs-lookup"><span data-stu-id="cdae4-105">You have added a reference to an assembly (assembly1) that has the `Embed Interop Types` property set to `True`.</span></span> <span data-ttu-id="cdae4-106">Это указывает компилятору на необходимость внедрить сведения о типе взаимодействия из этой сборки.</span><span class="sxs-lookup"><span data-stu-id="cdae4-106">This instructs the compiler to embed interop type information from that assembly.</span></span> <span data-ttu-id="cdae4-107">Тем не менее компилятор не может внедрить такие сведения из этой сборки, поскольку другая сборка, на которую задаются ссылки (сборка2), также ссылается на эту сборку (сборка1) и содержит свойство `Embed Interop Types` со значением `False`.</span><span class="sxs-lookup"><span data-stu-id="cdae4-107">However, the compiler cannot embed interop type information from that assembly because another assembly that you have referenced (assembly2) also references that assembly (assembly1) and has the `Embed Interop Types` property set to `False`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cdae4-108">Если присвоить свойству `Embed Interop Types` для ссылки на сборку значение `True`, это будет эквивалентно ссылке на сборку с использованием параметра `/link` для компилятора командной строки.</span><span class="sxs-lookup"><span data-stu-id="cdae4-108">Setting the `Embed Interop Types` property on an assembly reference to `True` is equivalent to referencing the assembly by using the `/link` option for the command-line compiler.</span></span>  
  
 <span data-ttu-id="cdae4-109">**Идентификатор ошибки:** BC40059</span><span class="sxs-lookup"><span data-stu-id="cdae4-109">**Error ID:** BC40059</span></span>  
  
### <a name="to-address-this-warning"></a><span data-ttu-id="cdae4-110">Устранение предупреждения</span><span class="sxs-lookup"><span data-stu-id="cdae4-110">To address this warning</span></span>  
  
-   <span data-ttu-id="cdae4-111">Чтобы внедрить сведения о типе взаимодействия для обеих сборок, присвойте свойству `Embed Interop Types` во всех ссылках на сборку сборка1 значение `True`.</span><span class="sxs-lookup"><span data-stu-id="cdae4-111">To embed interop type information for both assemblies, set the `Embed Interop Types` property on all references to assembly1 to `True`.</span></span>  
  
-   <span data-ttu-id="cdae4-112">Чтобы устранить это предупреждение, можно присвоить свойству `Embed Interop Types` сборки сборка1 значение `False`.</span><span class="sxs-lookup"><span data-stu-id="cdae4-112">To remove the warning, you can set the `Embed Interop Types` property of assembly1 to `False`.</span></span> <span data-ttu-id="cdae4-113">В этом случае сведения о типе взаимодействия предоставляется основной сборки взаимодействия (PIA).</span><span class="sxs-lookup"><span data-stu-id="cdae4-113">In this case, interop type information is provided by a primary interop assembly (PIA).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdae4-114">См. также</span><span class="sxs-lookup"><span data-stu-id="cdae4-114">See Also</span></span>  
 [<span data-ttu-id="cdae4-115">/link (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cdae4-115">/link (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/link.md)  
 [<span data-ttu-id="cdae4-116">Взаимодействие с неуправляемым кодом</span><span class="sxs-lookup"><span data-stu-id="cdae4-116">Interoperating with Unmanaged Code</span></span>](../../../framework/interop/index.md)
