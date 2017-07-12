---
title: "Раннее и позднее связывание (Visual Basic) | Документация Майкрософт"
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
- early binding
- objects [Visual Basic], late-bound
- objects [Visual Basic], early-bound
- objects [Visual Basic], late bound
- early binding, Visual Basic compiler
- binding, late and early
- objects [Visual Basic], early bound
- Visual Basic compiler, early and late binding
- late binding
- late binding, Visual Basic compiler
ms.assetid: d6ff7f1e-b94f-4205-ab8d-5cfa91758724
caps.latest.revision: 10
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
ms.translationtype: Human Translation
ms.sourcegitcommit: 31905a37f09db5f5192123f0118252fbe8b02eff
ms.openlocfilehash: 54b7e96c8b7cab8fba3dc295dfe124fcf3847118
ms.contentlocale: ru-ru
ms.lasthandoff: 05/26/2017

---
<a id="early-and-late-binding-visual-basic" class="xliff"></a>

# Раннее и позднее связывание (Visual Basic)
При присвоении переменной объекта компилятор [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] выполняет процесс, называемый связыванием (`binding`). Объект является объектом *с ранним связыванием*, если он присвоен переменной, объявленной с определенным типом объекта. Объекты с ранним связыванием позволяют компилятору выделять память и выполнять оптимизацию еще до запуска приложения. Например, в следующем фрагменте кода объявляется переменная типа <xref:System.IO.FileStream>:  
  
 [!code-vb[VbVbalrOOP#90](../../../../visual-basic/misc/codesnippet/VisualBasic/early-and-late-binding_1.vb)]  
  
 Так как <xref:System.IO.FileStream> — это тип конкретного объекта, для присвоенного переменной `FS` экземпляра происходит раннее связывание.  
  
 И наоборот, объект является объектом *с поздним связыванием*, если он присваивается переменной, объявленной с типом `Object`. Объекты этого типа могут содержать ссылки на любой объект, но теряют многие преимущества раннего связывания. Например, следующий фрагмент кода объявляет переменную объекта для хранения объекта, возвращаемого функцией `CreateObject`:  
  
 [!code-vb[VbVbalrOOP#91](../../../../visual-basic/misc/codesnippet/VisualBasic/early-and-late-binding_2.vb)]  
  
<a id="advantages-of-early-binding" class="xliff"></a>

## Преимущества раннего связывания  
 Раннее связывание объектов следует использовать везде, где это возможно, поскольку оно позволяет компилятору сделать важные оптимизации, повышающие эффективность приложений. Объекты с ранним связыванием работают значительно быстрее, чем объекты с поздним связыванием. Точное указание используемых объектов позволяет упростить чтение и обслуживание кода. Кроме того, раннее связывание позволяет использовать ряд дополнительных полезных возможностей, например автоматическое завершение кода и динамическую справку, поскольку интегрированная среда разработки (IDE) [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] может точно определить тип объекта при редактировании кода. Раннее связывание уменьшает количество и серьезность ошибок времени выполнения, так как позволяет компилятору фиксировать многие ошибки еще при компиляции программы.  
  
> [!NOTE]
>  Позднее связывание применимо только для доступа к членам типа, объявленным как `Public`. Доступ к членам, объявленным как `Friend` или `Protected Friend`, приводит к ошибке времени выполнения.  
  
<a id="see-also" class="xliff"></a>

## См. также  
 <xref:Microsoft.VisualBasic.Interaction.CreateObject%2A>   
 [Object Lifetime: How Objects Are Created and Destroyed (Visual Basic)](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)  (Время существования, создание и уничтожение объектов (Visual Basic))  
 [Тип данных Object](../../../../visual-basic/language-reference/data-types/object-data-type.md)
