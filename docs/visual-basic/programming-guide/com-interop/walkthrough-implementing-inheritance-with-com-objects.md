---
title: Пошаговое руководство. Реализация наследования с использованием COM-объектов (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- inheritance [Visual Basic], COM reusability
- base classes [Visual Basic], COM reusability
- inheritance [Visual Basic], walkthroughs
- derived classes [Visual Basic], COM reusability
ms.assetid: f8e7263a-de13-48d1-b67c-ca1adf3544d9
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 10c6bdf46e351b23705107da3b693531718cfd37
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="walkthrough-implementing-inheritance-with-com-objects-visual-basic"></a>Пошаговое руководство. Реализация наследования с использованием COM-объектов (Visual Basic)
Можно наследовать классы Visual Basic из `Public` классов в COM-объектами, даже тех, которые созданы в более ранних версиях Visual Basic. Свойства и методы классов, унаследованных от объектов COM можно переопределить или перегрузить только как свойства и методы базового класса можно переопределить или перегружен. Наследование от объектов COM полезно при наличии существующей библиотеки класса, не требуется повторной компиляции.  
  
 Ниже показано, как использовать Visual Basic 6.0 для создания COM-объекта, содержащего класс и его использование в качестве базового класса.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-build-the-com-object-that-is-used-in-this-walkthrough"></a>Для создания COM-объекта, который используется в этом пошаговом руководстве  
  
1.  В Visual Basic 6.0 откройте новый проект ActiveX библиотеки DLL. Проект с именем `Project1` создается. Он имеет класс с именем `Class1`.  
  
2.  В **обозревателя проектов**, щелкните правой кнопкой мыши **Project1**, а затем нажмите кнопку **свойства Project1**. **Свойства проекта** диалоговое окно.  
  
3.  На **Общие** вкладке **свойства проекта** диалоговом окне измените имя проекта, введя `ComObject1` в **имя проекта** поля.  
  
4.  В **обозревателя проектов**, щелкните правой кнопкой мыши `Class1`, а затем нажмите кнопку **свойства**. **Свойства** откроется окно для класса.  
  
5.  Изменение `Name` свойства `MathFunctions`.  
  
6.  В **обозревателя проектов**, щелкните правой кнопкой мыши `MathFunctions`, а затем нажмите кнопку **Просмотр кода**. **Редактор кода** отображается.  
  
7.  Добавьте локальную переменную для хранения значения свойства:  
  
    ```  
    ' Local variable to hold property value  
    Private mvarProp1 As Integer  
    ```  
  
8.  Добавить свойство `Let` и свойство `Get` процедуры свойств:  
  
    ```  
    Public Property Let Prop1(ByVal vData As Integer)  
       'Used when assigning a value to the property.  
       mvarProp1 = vData  
    End Property  
    Public Property Get Prop1() As Integer  
       'Used when retrieving a property's value.  
       Prop1 = mvarProp1  
    End Property  
    ```  
  
9. Добавление функции:  
  
    ```  
    Function AddNumbers(   
       ByVal SomeNumber As Integer,   
       ByVal AnotherNumber As Integer) As Integer  
  
       AddNumbers = SomeNumber + AnotherNumber  
    End Function  
    ```  
  
10. Создайте и зарегистрируйте объект COM, щелкнув **Создать ComObject1.dll** на **файл** меню.  
  
    > [!NOTE]
    >  Несмотря на то, что также можно представить класс, созданный с помощью Visual Basic как объект COM, он не является объектом COM и не может использоваться в этом пошаговом руководстве. Дополнительные сведения см. в разделе [COM-взаимодействие в приложениях .NET Framework](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).  
  
## <a name="interop-assemblies"></a>Сборки взаимодействия  
 В следующей процедуре вы создадите сборку взаимодействия, которая выступает в качестве моста между неуправляемого кода (например, объект COM) и управляемым кодом [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] использует. Сборки взаимодействия, который создает Visual Basic обрабатывает большую часть особенностей работы с объектами COM, такие как *маршалинг взаимодействия*, процесс упаковки параметров и возвращаемых значений, в эквивалентное ему данные типы, как они перемещаются и из COM-объектов. Сборку взаимодействия, а не к самому объекту COM. указывает ссылка в приложение Visual Basic.  
  
#### <a name="to-use-a-com-object-with-visual-basic-2005-and-later-versions"></a>Для использования COM-объекта с Visual Basic 2005 и более поздних версий  
  
1.  Откройте новый проект приложения Windows в Visual Basic.  
  
2.  В меню **Проект** щелкните команду **Добавить ссылку**.  
  
     Появится диалоговое окно **Добавление ссылки**.  
  
3.  На **COM** дважды щелкните `ComObject1` в **имя компонента** списке и нажмите кнопку **ОК**.  
  
4.  В меню **Проект** выберите пункт **Добавить новый элемент**.  
  
     Откроется диалоговое окно **Добавление нового элемента**.  
  
5.  В **шаблоны** области, нажмите кнопку **класса**.  
  
     Имя файла по умолчанию `Class1.vb`, отображается в **имя** поля. Измените значение поля на MathClass.vb и нажмите кнопку **добавить**. При этом создается класс с именем `MathClass`и отображает его код.  
  
6.  Добавьте следующий код в начало `MathClass` для наследования от класса COM.  
  
     [!code-vb[VbVbalrInterop#31](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_1.vb)]  
  
7.  Перегрузите открытый метод базового класса, добавив следующий код в `MathClass`:  
  
     [!code-vb[VbVbalrInterop#32](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_2.vb)]  
  
8.  Расширьте наследуемый класс, добавив следующий код в `MathClass`:  
  
     [!code-vb[VbVbalrInterop#33](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_3.vb)]  
  
 Новый класс наследует свойства базового класса в COM-объекта, перегружает метод и определяет новый метод для расширения класса.  
  
#### <a name="to-test-the-inherited-class"></a>Чтобы проверить унаследованный класс  
  
1.  Добавьте в форму запуска и дважды щелкните его, чтобы просмотреть код.  
  
2.  На кнопке панели `Click` процедуры обработчика событий, добавьте следующий код для создания экземпляра `MathClass` и вызовите перегруженные методы:  
  
     [!code-vb[VbVbalrInterop#34](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_4.vb)]  
  
3.  Запустите проект, нажав клавишу F5.  
  
 При нажатии кнопки в форме `AddNumbers` сначала вызывается метод с `Short` чисел, тип данных и Visual Basic выбирает соответствующий метод из базового класса. Второй вызов `AddNumbers` направляется в перегруженный метод `MathClass`. Третий вызов вызовы `SubtractNumbers` метод, который расширяет класс. Свойство в базовом классе, и выводится значение.  
  
## <a name="next-steps"></a>Следующие шаги  
 Возможно, вы заметили, перегруженных `AddNumbers` имеет тот же тип данных, метод, унаследованный от базового класса COM-объекта. Это так, как аргументы и параметры метода базового класса определены как 16-битовых целых чисел в Visual Basic 6.0, но они представляются как 16-битовых целых чисел типа `Short` в более поздних версиях Visual Basic. Новая функция поддерживает 32-битовых целых чисел и перегружает функцию базового класса.  
  
 При работе с COM-объектами, убедиться в том, что размер и типы данных параметров. Например при использовании COM-объекта, который принимает в качестве аргумента объект коллекции Visual Basic 6.0 не предоставляют набор из более поздней версии Visual Basic.  
  
 Свойства и методы, унаследованные из классов COM можно переопределить, это означает, что можно объявить локальное свойство или метод, который заменяет свойство или метод, унаследованный от базового класса COM. Правила переопределения наследуемых свойств COM аналогичны правилам переопределения других свойств и методов со следующими исключениями:  
  
-   При переопределении свойства или методы, унаследованные от класса COM, необходимо переопределить все остальные унаследованные свойства и методы.  
  
-   Свойства, использующие `ByRef` параметров не может быть переопределен.  
  
## <a name="see-also"></a>См. также  
 [COM-взаимодействие в приложениях .NET Framework](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)  
 [Оператор Inherits](../../../visual-basic/language-reference/statements/inherits-statement.md)  
 [Тип данных Short](../../../visual-basic/language-reference/data-types/short-data-type.md)
