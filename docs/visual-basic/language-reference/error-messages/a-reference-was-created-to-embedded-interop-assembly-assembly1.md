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
ms.openlocfilehash: bc2fbb044fc839aa24abf3dc1ea864457efb0653
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="a-reference-was-created-to-embedded-interop-assembly-39ltassembly1gt39-because-of-an-indirect-reference-to-that-assembly-from-assembly-39ltassembly2gt39"></a>Была создана ссылка на внедренную сборку взаимодействия &#39; &lt;assembly1&gt;&#39; из-за наличия неявной ссылки на эту сборку из сборки &#39;&lt; Assembly2&gt;&#39;
Была создана ссылка на внедренную сборку взаимодействия "\<сборка1>" из-за косвенной ссылки на эту сборку из сборки "\<сборка2>". Рекомендуется изменить свойство "Внедрить типы взаимодействия" в одной из сборок.  
  
 Была добавлена ссылка на сборку (сборка1), для которой свойству `Embed Interop Types` присвоено значение `True`. Это указывает компилятору на необходимость внедрить сведения о типе взаимодействия из этой сборки. Тем не менее компилятор не может внедрить такие сведения из этой сборки, поскольку другая сборка, на которую задаются ссылки (сборка2), также ссылается на эту сборку (сборка1) и содержит свойство `Embed Interop Types` со значением `False`.  
  
> [!NOTE]
>  Если присвоить свойству `Embed Interop Types` для ссылки на сборку значение `True`, это будет эквивалентно ссылке на сборку с использованием параметра `/link` для компилятора командной строки.  
  
 **Идентификатор ошибки:** BC40059  
  
### <a name="to-address-this-warning"></a>Устранение предупреждения  
  
-   Чтобы внедрить сведения о типе взаимодействия для обеих сборок, присвойте свойству `Embed Interop Types` во всех ссылках на сборку сборка1 значение `True`.  
  
-   Чтобы устранить это предупреждение, можно присвоить свойству `Embed Interop Types` сборки сборка1 значение `False`. В этом случае сведения о типе взаимодействия предоставляется основной сборки взаимодействия (PIA).  
  
## <a name="see-also"></a>См. также  
 [/link (Visual Basic)](../../../visual-basic/reference/command-line-compiler/link.md)  
 [Программирование с использованием основных сборок взаимодействия](http://msdn.microsoft.com/en-us/306fa1d6-0703-4004-9e93-d0a57f1be81e)
