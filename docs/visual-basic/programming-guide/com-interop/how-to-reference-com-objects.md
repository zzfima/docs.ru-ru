---
title: Практическое руководство. Ссылаться на COM-объекты из Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- COM interop [Visual Basic], referencing COM objects
- referencing objects, COM objects from Visual Basic
- objects [Visual Basic], referencing
- COM objects, referencing
- interop assemblies
ms.assetid: 9c518fb4-27d9-4112-9e6a-5a7d0210af6f
ms.openlocfilehash: df234ecaf25243dbdf2d6552942ca86001d4a6fe
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2019
ms.locfileid: "65592178"
---
# <a name="how-to-reference-com-objects-from-visual-basic"></a>Практическое руководство. Ссылаться на COM-объекты из Visual Basic
В Visual Basic Добавление ссылок на COM-объекты, имеющие библиотеки типов необходимо создать сборку взаимодействия для COM-библиотеки. Ссылки на члены объекта COM направляются в сборку взаимодействия и затем перенаправляется на фактический объект COM. Отклики от объекта COM направляются в сборку взаимодействия и пересылаются в приложение .NET Framework.  
  
 COM-объект можно ссылаться без использования сборки взаимодействия, внедряя сведения о типе для COM-объекта в сборку .NET. Чтобы внедрить сведения о типе, присвойте `Embed Interop Types` свойства `True` для ссылки на COM-объект. При компиляции с помощью компилятора командной строки, используйте `/link` параметр, чтобы ссылаться на библиотеки COM. Дополнительные сведения см. в разделе [/Link (Visual Basic)](../../../visual-basic/reference/command-line-compiler/link.md).  
  
 Visual Basic автоматически создает сборки взаимодействия, при добавлении ссылки на библиотеку типов из интегрированной среде разработки (IDE). При работе из командной строки, можно использовать служебную программу Tlbimp для создания сборки взаимодействия вручную.  
  
### <a name="to-add-references-to-com-objects"></a>Добавление ссылок на COM-объекты  
  
1. На **проекта** меню, выберите **добавить ссылку** и нажмите кнопку **COM** вкладки в диалоговом окне.  
  
2. Выберите компонент, который вы хотите использовать в списке COM-объектов.  
  
3. Чтобы упростить доступ к сборке взаимодействия, добавьте `Imports` в начало класса или модуля, в котором используется COM-объекта. Например, в следующем примере кода импортирует пространство имен `INKEDLib` для объектов, на которые ссылается `Microsoft InkEdit Control 1.0` библиотеки.  
  
     [!code-vb[VbVbalrInterop#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#40)]  
  
### <a name="to-create-an-interop-assembly-using-tlbimp"></a>Чтобы создать сборку взаимодействия, при помощи средства Tlbimp  
  
1. Добавьте расположение Tlbimp в путь поиска, если он уже не является частью пути поиска, и вы находитесь не в настоящее время в каталоге, в котором он находится.  
  
2. Вызовите программу Tlbimp из командной строки, указав следующие сведения:  
  
    - Имя и расположение библиотеки DLL, которая содержит библиотеки типов  
  
    - Имя и расположение пространства имен, где должны размещаться данные  
  
    - Имя и расположение целевой сборки взаимодействия  
  
     Примером является следующий код:  
  
    ```  
    Tlbimp test3.dll /out:NameSpace1 /out:Interop1.dll  
    ```  
  
     Tlbimp можно использовать для создания сборки взаимодействия для библиотек типов, даже для отмены регистрации COM-объектов. Тем не менее COM-объекты, на который ссылается сборки взаимодействия должны быть правильно зарегистрированы на компьютере, где они будут использоваться. COM-объект можно зарегистрировать с помощью служебной программы Regsvr32, включенные в операционную систему Windows.  
  
## <a name="see-also"></a>См. также

- [COM-взаимодействие](../../../visual-basic/programming-guide/com-interop/index.md)
- [Tlbimp.exe (программа экспорта библиотек типов)](../../../framework/tools/tlbimp-exe-type-library-importer.md)
- [Tlbexp.exe (программа экспорта библиотек типов)](../../../framework/tools/tlbexp-exe-type-library-exporter.md)
- [Пошаговое руководство: Реализация наследования с использованием COM-объектов](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)
- [Устранение неполадок взаимодействия](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)
- [Оператор Imports (пространство имен и тип .NET)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
