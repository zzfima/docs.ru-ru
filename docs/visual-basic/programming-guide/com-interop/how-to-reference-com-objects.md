---
title: Практическое руководство. Ссылка на COM-объект в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- COM interop [Visual Basic], referencing COM objects
- referencing objects, COM objects from Visual Basic
- objects [Visual Basic], referencing
- COM objects, referencing
- interop assemblies
ms.assetid: 9c518fb4-27d9-4112-9e6a-5a7d0210af6f
ms.openlocfilehash: 49f3da396ca5cd48b0cf454ce1ecd5422c28e38f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33643956"
---
# <a name="how-to-reference-com-objects-from-visual-basic"></a>Практическое руководство. Ссылка на COM-объект в Visual Basic
В Visual Basic Добавление ссылок на COM-объекты, имеющие библиотеки типов требует создания сборки взаимодействия для COM-библиотеки. Ссылки на члены объекта COM направляются в сборку взаимодействия и пересылаются на фактическое COM-объект. Ответы из COM-объекта направляются в сборку взаимодействия и пересылаются в вашей [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] приложения.  
  
 COM-объект можно ссылаться без использования сборки взаимодействия, внедрение сведений о типах COM-объекта в сборку .NET. Чтобы внедрить сведения о типе, присвойте `Embed Interop Types` свойства `True` для ссылки на COM-объект. При компиляции с помощью компилятора командной строки используйте `/link` для создания ссылки на библиотеку COM. Дополнительные сведения см. в разделе [/Link (Visual Basic)](../../../visual-basic/reference/command-line-compiler/link.md).  
  
 Visual Basic автоматически создает сборки взаимодействия при добавлении ссылки на библиотеку типов из интегрированной среды разработки (IDE). При работе в командной строке, можно использовать служебную программу Tlbimp для создания сборки взаимодействия вручную.  
  
### <a name="to-add-references-to-com-objects"></a>Для добавления ссылок на COM-объекты  
  
1.  На **проекта** меню, выберите **добавить ссылку** и нажмите кнопку **COM** вкладка в диалоговом окне.  
  
2.  Выберите компонент, который вы хотите использовать в списке COM-объектов.  
  
3.  Для упрощения доступа к сборке взаимодействия, добавьте `Imports` в начало класса или модуля, в котором будет использоваться COM-объекта. Например, в следующем примере кода выполняется импорт пространства имен `INKEDLib` для объектов, указанных в `Microsoft InkEdit Control 1.0` библиотеки.  
  
     [!code-vb[VbVbalrInterop#40](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/how-to-reference-com-objects_1.vb)]  
  
### <a name="to-create-an-interop-assembly-using-tlbimp"></a>Чтобы создать сборку взаимодействия с помощью Tlbimp  
  
1.  Добавьте расположение Tlbimp в путь поиска, если он уже не является частью пути поиска, и вы находитесь не в настоящее время в каталоге, где он расположен.  
  
2.  Вызовите программу Tlbimp из командной строки, указав следующие сведения:  
  
    -   Имя и расположение библиотеки DLL, которая содержит библиотеку типов  
  
    -   Имя и расположение пространства имен, где должны размещаться данные  
  
    -   Имя и расположение целевой сборки взаимодействия  
  
     Примером является следующий код:  
  
    ```  
    Tlbimp test3.dll /out:NameSpace1 /out:Interop1.dll  
    ```  
  
     Tlbimp можно использовать для создания сборок взаимодействия для библиотек типов, даже для незарегистрированных COM-объектов. Тем не менее COM-объекты, на который ссылается сборки взаимодействия должны быть правильно зарегистрированы на компьютере, где они будут использоваться. COM-объект можно зарегистрировать с помощью служебной программы Regsvr32, входящий в состав операционной системы Windows.  
  
## <a name="see-also"></a>См. также  
 [COM-взаимодействие](../../../visual-basic/programming-guide/com-interop/index.md)  
 [Tlbimp.exe (программа экспорта библиотек типов)](../../../framework/tools/tlbimp-exe-type-library-importer.md)  
 [Tlbexp.exe (программа экспорта библиотек типов)](http://msdn.microsoft.com/library/a487d61b-d166-467b-a7ca-d8b52fbff42d)  
 [Пошаговое руководство. Реализация наследования с использованием COM-объектов](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)  
 [Устранение неполадок взаимодействия](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)  
 [Оператор Imports (пространство имен и тип .NET)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
