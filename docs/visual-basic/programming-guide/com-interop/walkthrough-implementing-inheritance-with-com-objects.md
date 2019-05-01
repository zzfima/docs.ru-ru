---
title: Пошаговое руководство. Реализация наследования с использованием COM-объектов (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [Visual Basic], COM reusability
- base classes [Visual Basic], COM reusability
- inheritance [Visual Basic], walkthroughs
- derived classes [Visual Basic], COM reusability
ms.assetid: f8e7263a-de13-48d1-b67c-ca1adf3544d9
ms.openlocfilehash: 0b3977e73e3b2aa9e80e2dab08d15035283b8387
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62022328"
---
# <a name="walkthrough-implementing-inheritance-with-com-objects-visual-basic"></a>Пошаговое руководство. Реализация наследования с использованием COM-объектов (Visual Basic)
Можно создавать классы Visual Basic из `Public` классов в COM-объекты, даже были созданы в более ранних версиях Visual Basic. Свойства и методы классов, унаследованных от объектов COM могут быть переопределены или перегружены так же, как свойства и методы базового класса могут быть переопределены или перегружены. Наследование от COM-объектов используется, при наличии существующей библиотеки класса, перекомпиляция не требуется.  
  
 Ниже показано, как использовать Visual Basic 6.0 для создания COM-объект, который содержит класс, а затем использовать его в качестве базового класса.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-build-the-com-object-that-is-used-in-this-walkthrough"></a>Для создания COM-объект, который используется в этом пошаговом руководстве  
  
1. В Visual Basic 6.0 откройте новый проект ActiveX библиотеки DLL. Проект с именем `Project1` создается. Он имеет класс с именем `Class1`.  
  
2. В **обозревателя проектов**, щелкните правой кнопкой мыши **Project1**, а затем нажмите кнопку **свойства Project1**. **Свойства проекта** диалоговое окно.  
  
3. На **Общие** вкладке **свойства проекта** диалогового окна можно изменить имя проекта, введя `ComObject1` в **имя_проекта** поля.  
  
4. В **обозревателя проектов**, щелкните правой кнопкой мыши `Class1`, а затем нажмите кнопку **свойства**. **Свойства** откроется диалоговое окно для класса.  
  
5. Изменение `Name` свойства `MathFunctions`.  
  
6. В **обозревателя проектов**, щелкните правой кнопкой мыши `MathFunctions`, а затем нажмите кнопку **Просмотр кода**. **Редактор кода** отображается.  
  
7. Добавьте локальную переменную для хранения значения свойства:  
  
    ```  
    ' Local variable to hold property value  
    Private mvarProp1 As Integer  
    ```  
  
8. Добавить свойство `Let` и свойство `Get` процедуры свойств:  
  
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
  
10. Создание и регистрация COM-объект, щелкнув **Создать ComObject1.dll** на **файл** меню.  
  
    > [!NOTE]
    >  Несмотря на то, что пользователь может предоставить класс, созданный в Visual Basic как объект COM, он не является истинным COM-объектом и не может использоваться в этом пошаговом руководстве. Дополнительные сведения см. в разделе [COM-взаимодействие в приложениях .NET Framework](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).  
  
## <a name="interop-assemblies"></a>Сборки взаимодействия  
 В следующей процедуре вы создадите сборку взаимодействия, который выступает в качестве моста между неуправляемым кодом (например, COM-объекта) и управляемым кодом, который использует Visual Studio. Сборки взаимодействия, который создает Visual Basic обрабатывает многие детали работы с объектами COM, такие как *маршалинг взаимодействия*, процесс упаковки параметров и возвращаемых значений в данных типов при переходе и из COM-объектов. Ссылка на сборку взаимодействия, а не к самому объекту COM. в пунктах приложения Visual Basic.  
  
#### <a name="to-use-a-com-object-with-visual-basic-2005-and-later-versions"></a>Для использования COM-объекта с помощью Visual Basic 2005 и более поздних версий  
  
1. Откройте новый проект приложения Windows на Visual Basic.  
  
2. В меню **Проект** щелкните команду **Добавить ссылку**.  
  
     Появится диалоговое окно **Добавление ссылки**.  
  
3. На **COM** дважды щелкните `ComObject1` в **имя компонента** списке и нажмите кнопку **ОК**.  
  
4. В меню **Проект** выберите пункт **Добавить новый элемент**.  
  
     Откроется диалоговое окно **Добавление нового элемента**.  
  
5. В **шаблоны** панели щелкните **класс**.  
  
     Имя файла по умолчанию, `Class1.vb`, отображается в **имя** поля. Это поле следует изменять MathClass.vb и нажмите кнопку **добавить**. Это создает класс с именем `MathClass`и отображает его код.  
  
6. Добавьте следующий код в верхнюю часть `MathClass` для наследования от класса COM.  
  
     [!code-vb[VbVbalrInterop#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#31)]  
  
7. Перегрузите открытый метод базового класса, добавив следующий код, чтобы `MathClass`:  
  
     [!code-vb[VbVbalrInterop#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#32)]  
  
8. Расширить наследуемого класса, добавив следующий код, чтобы `MathClass`:  
  
     [!code-vb[VbVbalrInterop#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#33)]  
  
 Новый класс наследует свойства базового класса в COM-объекта, перегружающий метод и определяет новый метод для расширения класса.  
  
#### <a name="to-test-the-inherited-class"></a>Чтобы проверить унаследованный класс  
  
1. Добавьте кнопку в форму запуска и дважды щелкните его, чтобы просмотреть ее код.  
  
2. На кнопке панели `Click` процедуры обработчика событий, добавьте следующий код для создания экземпляра `MathClass` и вызова перегруженных методов:  
  
     [!code-vb[VbVbalrInterop#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#34)]  
  
3. Запустите проект, нажав клавишу F5.  
  
 При нажатии кнопки в форме `AddNumbers` с первого вызова метода `Short` данных введите числа, и Visual Basic выбирает соответствующий метод из базового класса. Второй вызов `AddNumbers` направляется в перегруженный метод `MathClass`. Третий вызов вызовы `SubtractNumbers` метод, который расширяет класс. Свойству в базовом классе, а значение отображается.  
  
## <a name="next-steps"></a>Следующие шаги  
 Вы могли заметить, перегруженных `AddNumbers` имеет тот же тип данных, метод, унаследованный от базового класса COM-объекта. Это обусловлено тем, аргументы и параметры метода базового класса определяются как 16-разрядных целых чисел в Visual Basic 6.0, но они представляются как 16-разрядных целых чисел типа `Short` в более поздних версиях Visual Basic. Новая функция поддерживает 32-разрядных целых чисел и перегружает функцию базового класса.  
  
 При работе с COM-объектов, убедитесь, что проверить размер и типы данных параметров. Например при использовании COM-объект, который принимает в качестве аргумента объект коллекции Visual Basic 6.0, невозможно использовать коллекцию в поздних версиях Visual Basic.  
  
 Свойства и методы, унаследованные от COM-классов можно переопределить, это означает, что можно объявить локальное свойство или метод, который заменяет свойство или метод, унаследованный от базового класса COM. Правила переопределения наследуемых свойств COM аналогичны правилам переопределения других свойств и методов, за исключением следующих случаев:  
  
- При переопределении свойства или методы, унаследованные от класса COM, необходимо переопределить все остальные унаследованные свойства и методы.  
  
- Свойства, использующие `ByRef` параметров не может быть переопределен.  
  
## <a name="see-also"></a>См. также

- [COM-взаимодействие в приложениях .NET Framework](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)
- [Оператор Inherits](../../../visual-basic/language-reference/statements/inherits-statement.md)
- [Тип данных Short](../../../visual-basic/language-reference/data-types/short-data-type.md)
