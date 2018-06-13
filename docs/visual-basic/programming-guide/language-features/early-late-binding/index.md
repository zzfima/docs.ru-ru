---
title: Раннее и позднее связывание (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- early binding [Visual Basic]
- objects [Visual Basic], late-bound
- objects [Visual Basic], early-bound
- objects [Visual Basic], late bound
- early binding [Visual Basic], Visual Basic compiler
- binding [Visual Basic], late and early
- objects [Visual Basic], early bound
- Visual Basic compiler, early and late binding
- late binding [Visual Basic]
- late binding [Visual Basic], Visual Basic compiler
ms.assetid: d6ff7f1e-b94f-4205-ab8d-5cfa91758724
ms.openlocfilehash: 8426899b0c0d3649f47cbd6ad5383dd3c95b9499
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33647258"
---
# <a name="early-and-late-binding-visual-basic"></a>Раннее и позднее связывание (Visual Basic)
Компилятор Visual Basic выполняет процесс, называемый `binding` при присвоении переменной объекта. Объект является объектом *с ранним связыванием*, если он присвоен переменной, объявленной с определенным типом объекта. Объекты с ранним связыванием позволяют компилятору выделять память и выполнять оптимизацию еще до запуска приложения. Например, в следующем фрагменте кода объявляется переменная типа <xref:System.IO.FileStream>:  
  
 [!code-vb[VbVbalrOOP#90](../../../../visual-basic/misc/codesnippet/VisualBasic/early-and-late-binding_1.vb)]  
  
 Так как <xref:System.IO.FileStream> — это тип конкретного объекта, для присвоенного переменной `FS` экземпляра происходит раннее связывание.  
  
 И наоборот, объект является объектом *с поздним связыванием*, если он присваивается переменной, объявленной с типом `Object`. Объекты этого типа могут содержать ссылки на любой объект, но теряют многие преимущества раннего связывания. Например, следующий фрагмент кода объявляет переменную объекта для хранения объекта, возвращаемого функцией `CreateObject`:  
  
 [!code-vb[VbVbalrOOP#91](../../../../visual-basic/misc/codesnippet/VisualBasic/early-and-late-binding_2.vb)]  
  
## <a name="advantages-of-early-binding"></a>Преимущества раннего связывания  
 Раннее связывание объектов следует использовать везде, где это возможно, поскольку оно позволяет компилятору сделать важные оптимизации, повышающие эффективность приложений. Объекты с ранним связыванием работают значительно быстрее, чем объекты с поздним связыванием. Точное указание используемых объектов позволяет упростить чтение и обслуживание кода. Является еще одним преимуществом использования для раннее связывание, что позволяет полезные возможности, такие как автоматическое завершение кода и Динамическая справка среды разработки Visual Studio (IDE) может точно определять тип объекта при редактировании код. Раннее связывание уменьшает количество и серьезность ошибок времени выполнения, так как позволяет компилятору фиксировать многие ошибки еще при компиляции программы.  
  
> [!NOTE]
>  Позднее связывание применимо только для доступа к членам типа, объявленным как `Public`. Доступ к членам, объявленным как `Friend` или `Protected Friend`, приводит к ошибке времени выполнения.  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.Interaction.CreateObject%2A>  
 [Время существования. Создание и уничтожение объектов](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)  
 [Тип данных Object](../../../../visual-basic/language-reference/data-types/object-data-type.md)
