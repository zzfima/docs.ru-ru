---
title: "Практическое руководство: ссылка на объект COM в Visual Basic | Документы Microsoft"
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
- COM interop, referencing COM objects
- referencing objects, COM objects from Visual Basic
- objects [Visual Basic], referencing
- COM objects, referencing
- interop assemblies
ms.assetid: 9c518fb4-27d9-4112-9e6a-5a7d0210af6f
caps.latest.revision: 13
author: stevehoag
ms.author: shoag
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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 97c132bcbd36ba7810acadb2aebddc5e84f0b44d
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-reference-com-objects-from-visual-basic"></a>Практическое руководство. Ссылка на COM-объект в Visual Basic
В [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], добавление ссылок на COM-объекты, имеющие библиотеки типов необходимо создать сборку взаимодействия для COM-библиотеки. Ссылки на члены объекта COM направляются в сборку взаимодействия и пересылаются на фактическое COM-объект. Отклики от объекта COM направляются в сборку взаимодействия и пересылаются на [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] приложения.  
  
 COM-объект можно ссылаться без использования сборки взаимодействия путем встраивания сведения о типе для COM-объекта в сборку .NET. Чтобы внедрить сведения о типе, присвойте `Embed Interop Types` свойства `True` для ссылки на COM-объект. Если компиляция производится с помощью компилятора командной строки, используйте `/link` возможность ссылки на библиотеку COM. Дополнительные сведения см. в разделе [/Link (Visual Basic)](../../../visual-basic/reference/command-line-compiler/link.md).  
  
 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]автоматически создает сборки взаимодействия при добавлении ссылки на библиотеку типов из интегрированной среды разработки (IDE). При работе из командной строки можно использовать средство Tlbimp для создания сборок взаимодействия вручную.  
  
### <a name="to-add-references-to-com-objects"></a>Добавление ссылок на COM-объекты  
  
1.  На **проекта** меню, выберите **добавить ссылку** и нажмите кнопку **COM** вкладки в диалоговом окне.  
  
2.  Выберите компонент, который вы хотите использовать в списке COM-объектов.  
  
3.  Для упрощения доступа к сборке взаимодействия добавьте `Imports` инструкции в начало класса или модуля, в котором будет использоваться COM-объекта. Например, в следующем примере кода импортирует пространство имен `INKEDLib` для объектов, указанных в `Microsoft InkEdit Control 1.0` библиотеки.  
  
     [!code-vb[VbVbalrInterop&#40;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/how-to-reference-com-objects_1.vb)]  
  
### <a name="to-create-an-interop-assembly-using-tlbimp"></a>Чтобы создать сборку взаимодействия при помощи средства Tlbimp  
  
1.  Добавьте расположение Tlbimp в путь поиска, если он уже не является частью пути поиска и настоящее время вы не в каталоге, в котором он находится.  
  
2.  Вызовите программу Tlbimp из командной строки, указав следующие сведения:  
  
    -   Имя и расположение библиотеки DLL, содержащего библиотеку типов  
  
    -   Имя и расположение пространства имен, где должна быть размещена информация  
  
    -   Имя и расположение целевой сборки взаимодействия  
  
     Примером является следующий код:  
  
    ```  
    Tlbimp test3.dll /out:NameSpace1 /out:Interop1.dll  
    ```  
  
     Tlbimp можно использовать для создания сборок взаимодействия для библиотек типов, даже для незарегистрированных COM-объектов. Тем не менее COM-объекты, на которые ссылается на сборки взаимодействия должны быть правильно зарегистрированы на компьютере, где они будут использоваться. Можно зарегистрировать объект COM при помощи программы Regsvr32, входящий в состав операционной системы Windows.  
  
## <a name="see-also"></a>См. также  
 [Взаимодействие COM](../../../visual-basic/programming-guide/com-interop/index.md)   
 [Tlbimp.exe (программа импорта библиотек типов)](http://msdn.microsoft.com/library/ec0a8d63-11b3-4acd-b398-da1e37e97382)   
 [Tlbexp.exe (программа экспорта библиотек типов)](http://msdn.microsoft.com/library/a487d61b-d166-467b-a7ca-d8b52fbff42d)   
 [Пошаговое руководство: Реализация наследования с использованием COM-объектов](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)   
 [Устранение неполадок взаимодействия](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)   
 [Оператор Imports (пространство имен и тип .NET)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
