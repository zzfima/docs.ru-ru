---
title: "Пошаговое руководство: Реализация наследования с использованием COM-объектов (Visual Basic) | Документы Microsoft"
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
- inheritance, COM reusability
- base classes, COM reusability
- inheritance, walkthroughs
- derived classes, COM reusability
ms.assetid: f8e7263a-de13-48d1-b67c-ca1adf3544d9
caps.latest.revision: 16
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
ms.openlocfilehash: fa7753847619f14600c924cba01e55651c4f17c2
ms.lasthandoff: 03/13/2017

---
# <a name="walkthrough-implementing-inheritance-with-com-objects-visual-basic"></a>Пошаговое руководство. Реализация наследования с использованием COM-объектов (Visual Basic)
Создавать производные классы Visual Basic из можно `Public` классов в COM-объекты, даже те, которые созданы в более ранних версиях [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]. Свойства и методы классов, унаследованных от объектов COM можно переопределить или перегрузить как свойства и методы базового класса можно переопределить или перегружен. Наследование от объектов COM используется, при наличии созданную библиотеку классов нежелательно перекомпилировать.  
  
 Ниже показано, как использовать Visual Basic 6.0 для создания COM-объект, содержащий класс, а затем использовать его в качестве базового класса.  
  
[!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### <a name="to-build-the-com-object-that-is-used-in-this-walkthrough"></a>Чтобы создать объект COM, используемый в данном пошаговом руководстве  
  
1.  В Visual Basic 6.0 откройте новый проект ActiveX DLL. Проект с именем `Project1` создается. Он имеет класс с именем `Class1`.  
  
2.  В **обозревателя проектов**, щелкните правой кнопкой мыши **Project1**, а затем нажмите кнопку **свойства Project1**. **Свойства проекта** диалоговое окно.  
  
3.  На **Общие** вкладке **свойства проекта** диалоговом окне измените имя проекта, введя `ComObject1` в **имя проекта** поле.  
  
4.  В **обозревателя проектов**, щелкните правой кнопкой мыши `Class1`, а затем нажмите кнопку **свойства**. **Свойства** откроется окно для класса.  
  
5.  Изменение `Name` свойства `MathFunctions`.  
  
6.  В **обозревателя проектов**, щелкните правой кнопкой мыши `MathFunctions`, а затем нажмите кнопку **Просмотр кода**. **Редактор кода** отображается.  
  
7.  Добавьте локальную переменную для хранения значения свойства:  
  
    ```  
    ' Local variable to hold property value  
    Private mvarProp1 As Integer  
    ```  
  
8.  Добавьте свойство `Let` и свойство `Get` процедуры свойств:  
  
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
  
9. Добавьте функцию:  
  
    ```  
    Function AddNumbers(   
       ByVal SomeNumber As Integer,   
       ByVal AnotherNumber As Integer) As Integer  
  
       AddNumbers = SomeNumber + AnotherNumber  
    End Function  
    ```  
  
10. Создайте и зарегистрируйте объект COM, щелкнув **Создать ComObject1.dll** на **файл** меню.  
  
    > [!NOTE]
    >  Несмотря на то, что пользователь может предоставить класс, созданный в [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] как COM-объект не является объектом COM и не может использоваться в этом пошаговом руководстве. Дополнительные сведения см. в разделе [COM-взаимодействие в приложениях .NET Framework](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).  
  
## <a name="interop-assemblies"></a>Сборки взаимодействия  
 В следующей процедуре будет создать сборку взаимодействия, которая действует как мост между неуправляемым кодом (например, объект COM) и управляемым кодом [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] использует. Сборки взаимодействия, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] обеспечивает различные аспекты работы с COM-объектами, такие как *маршалинг взаимодействия*, процесс упаковки параметров и возвращения значений в данных типов при передаче в объекты COM и обратно. Ссылка в [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] точки приложения сборку взаимодействия, а не к самому объекту COM..  
  
#### <a name="to-use-a-com-object-with-visual-basic-2005-and-later-versions"></a>Для использования COM-объекта с помощью Visual Basic 2005 и более поздних версий  
  
1.  Откройте новую [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] проекта приложения Windows.  
  
2.  На **проекта** меню, щелкните **добавить ссылку**.  
  
     **Добавить ссылку** диалоговое окно.  
  
3.  На **COM** дважды щелкните `ComObject1` в **имя компонента** списке и нажмите кнопку **ОК**.  
  
4.  В меню **Проект** выберите пункт **Добавить новый элемент**.  
  
     **Add New Item** диалоговое окно.  
  
5.  В **шаблоны** область, нажмите кнопку **класса**.  
  
     Имя файла по умолчанию `Class1.vb`, отображается в **имя** поле. Измените значение поля на MathClass.vb и нажмите кнопку **добавить**. При этом создается класс с именем `MathClass`и отобразит его код.  
  
6.  Добавьте следующий код в начало `MathClass` для наследования от класса COM.  
  
     [!code-vb[VbVbalrInterop&#31;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_1.vb)]  
  
7.  Перегрузите открытый метод базового класса, добавив следующий код в `MathClass`:  
  
     [!code-vb[VbVbalrInterop&#32;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_2.vb)]  
  
8.  Расширьте наследуемый класс, добавив следующий код в `MathClass`:  
  
     [!code-vb[VbVbalrInterop&#33;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_3.vb)]  
  
 Новый класс наследует свойства базового класса в объекте COM, перегружает метод и определяет новый метод для расширения класса.  
  
#### <a name="to-test-the-inherited-class"></a>Чтобы проверить унаследованный класс  
  
1.  Добавьте кнопку в форму запуска и дважды щелкните его для просмотра его кода.  
  
2.  Для кнопки `Click` процедуры обработчика событий, добавьте следующий код для создания экземпляра `MathClass` и вызовите перегруженные методы:  
  
     [!code-vb[VbVbalrInterop&#34;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_4.vb)]  
  
3.  Запустите проект, нажав клавишу F5.  
  
 При нажатии кнопки в форме `AddNumbers` сначала вызывается метод с `Short` чисел, тип данных и [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] выбирает соответствующий метод из базового класса. Второй вызов `AddNumbers` направляется в перегруженный метод `MathClass`. Третий вызов вызовы `SubtractNumbers` метод, который расширяет класс. Свойство в базовом классе, и отображается значение.  
  
## <a name="next-steps"></a>Дальнейшие действия  
 Вы могли заметить, перегруженных `AddNumbers` имеет тот же тип данных, метод, унаследованный от базового класса COM-объекта. Это потому, что аргументы и параметры метода базового класса определены как 16-битовых целых чисел в Visual Basic 6.0, но они представляются как 16-битовых целых чисел типа `Short` в более поздних версиях Visual Basic. Новая функция поддерживает 32-разрядные целые значения и перегружает функцию базового класса.  
  
 При работе с COM-объектами, убедитесь в правильности размера и типов данных параметров. Например при использовании COM-объекта, который принимает в качестве аргумента объект коллекции Visual Basic 6.0, невозможно использовать коллекцию из более поздней версии Visual Basic.  
  
 Свойства и методы, унаследованные из классов COM можно переопределить, это означает, что можно объявить локальное свойство или метод, который заменяет свойство или метод, унаследованный от базового класса COM. Правила переопределения унаследованных свойств COM аналогичны правилам переопределения других свойств и методов со следующими исключениями:  
  
-   При переопределении свойства или методы, унаследованные от класса COM, необходимо переопределить все остальные унаследованные свойства и методы.  
  
-   Свойства, использующие `ByRef` параметров не может быть переопределен.  
  
## <a name="see-also"></a>См. также  
 [COM-взаимодействие в приложениях .NET Framework](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)   
 [Оператор Inherits](../../../visual-basic/language-reference/statements/inherits-statement.md)   
 [Тип данных Short](../../../visual-basic/language-reference/data-types/short-data-type.md)
