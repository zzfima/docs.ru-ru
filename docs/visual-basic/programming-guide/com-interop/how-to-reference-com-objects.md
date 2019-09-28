---
title: Практическое руководство. Ссылки на COM-объекты из Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- COM interop [Visual Basic], referencing COM objects
- referencing objects, COM objects from Visual Basic
- objects [Visual Basic], referencing
- COM objects, referencing
- interop assemblies
ms.assetid: 9c518fb4-27d9-4112-9e6a-5a7d0210af6f
ms.openlocfilehash: 8e502dc9a279d9271a61fd2cf7a6afb564f09125
ms.sourcegitcommit: da2dd2772fcf32b44eb18b1cbe8affd17b1753c9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/27/2019
ms.locfileid: "71351996"
---
# <a name="how-to-reference-com-objects-from-visual-basic"></a>Практическое руководство. Ссылки на COM-объекты из Visual Basic
В Visual Basic добавление ссылок на COM-объекты, имеющие библиотеки типов, требует создания сборки взаимодействия для библиотеки COM. Ссылки на члены COM-объекта направляются в сборку взаимодействия, а затем пересылаются на фактический COM-объект. Ответы от COM-объекта направляются в сборку взаимодействия и пересылаются в приложение .NET Framework.  
  
 Вы можете ссылаться на COM-объект без использования сборки взаимодействия, внедрив сведения о типе для COM-объекта в сборку .NET. Чтобы внедрить сведения о типе, задайте для свойства `Embed Interop Types` значение `True` для ссылки на COM-объект. При компиляции с помощью компилятора командной строки используйте параметр `/link` для ссылки на библиотеку COM. Дополнительные сведения см. в разделе [/Link (Visual Basic)](../../../visual-basic/reference/command-line-compiler/link.md).  
  
 Visual Basic автоматически создает сборки взаимодействия при добавлении ссылки на библиотеку типов из интегрированной среды разработки (IDE). При работе из командной строки можно использовать служебную программу Tlbimp для создания сборок взаимодействия вручную.  
  
### <a name="to-add-references-to-com-objects"></a>Добавление ссылок на COM-объекты  
  
1. В меню **проект** выберите команду **Добавить ссылку** , а затем откройте вкладку **com** в диалоговом окне.  
  
2. Выберите компонент, который вы хотите использовать, из списка COM-объектов.  
  
3. Чтобы упростить доступ к сборке взаимодействия, добавьте оператор `Imports` в начало класса или модуля, в котором будет использоваться COM-объект. Например, в следующем примере кода выполняется импорт пространства имен `INKEDLib` для объектов, на которые имеются ссылки в библиотеке `Microsoft InkEdit Control 1.0`.  
  
     [!code-vb[VbVbalrInterop#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#40)]  
  
### <a name="to-create-an-interop-assembly-using-tlbimp"></a>Создание сборки взаимодействия с помощью программы Tlbimp  
  
1. Добавьте расположение программы Tlbimp в путь поиска, если он еще не является частью пути поиска, и вы не находитесь в каталоге, в котором он находится.  
  
2. Вызовите программу Tlbimp из командной строки, предоставив следующую информацию:  
  
    - Имя и расположение библиотеки DLL, содержащей библиотеку типов  
  
    - Имя и расположение пространства имен, в которое следует поместить данные  
  
    - Имя и расположение целевой сборки взаимодействия  
  
     Примером является следующий код:  
  
    ```console  
    Tlbimp test3.dll /out:NameSpace1 /out:Interop1.dll  
    ```  
  
     Программу Tlbimp можно использовать для создания сборок взаимодействия для библиотек типов, даже для незарегистрированных COM-объектов. Однако COM-объекты, на которые ссылаются сборки взаимодействия, должны быть правильно зарегистрированы на компьютере, где они будут использоваться. Вы можете зарегистрировать COM-объект с помощью служебной программы regsvr32, входящей в состав операционной системы Windows.  
  
## <a name="see-also"></a>См. также

- [COM-взаимодействие](../../../visual-basic/programming-guide/com-interop/index.md)
- [Tlbimp.exe (программа экспорта библиотек типов)](../../../framework/tools/tlbimp-exe-type-library-importer.md)
- [Tlbexp.exe (программа экспорта библиотек типов)](../../../framework/tools/tlbexp-exe-type-library-exporter.md)
- [Пошаговое руководство: Реализация наследования с использованием COM-объектов](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)
- [Устранение неполадок взаимодействия](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)
- [Оператор Imports (пространство имен и тип .NET)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
