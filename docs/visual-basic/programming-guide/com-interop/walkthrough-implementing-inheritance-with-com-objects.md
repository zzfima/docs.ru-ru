---
title: "Пошаговое руководство. Реализация наследования с использованием COM-объектов (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "базовые классы, многократное использование COM"
  - "производные классы, многократное использование COM"
  - "наследование, многократное использование COM"
  - "наследование, пошаговые руководства"
ms.assetid: f8e7263a-de13-48d1-b67c-ca1adf3544d9
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Пошаговое руководство. Реализация наследования с использованием COM-объектов (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Создавать производные классы Visual Basic можно из классов `Public` в объектах COM, в том числе из классов, созданных в более ранних версиях [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  Свойства и методы классов, унаследованных от объектов COM, могут быть переопределены или перегружены таким же образом, как свойства и методы любого другого базового класса.  Наследование от объектов COM используется, если уже созданную библиотеку классов не требуется перекомпилировать.  
  
 Далее показано, как с помощью Visual Basic 6.0 создать объект COM, содержащий класс, а затем использовать его в качестве базового класса.  
  
 [!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### Чтобы построить объект COM, используемый в данном пошаговом руководстве  
  
1.  Откройте в Visual Basic 6.0 новый проект ActiveX DLL.  Создается проект с именем `Project1`.  Он имеет класс с именем `Class1`.  
  
2.  В **Обозревателе проекта** щелкните правой кнопкой мыши **Project1** и нажмите кнопку **Свойства Project1**.  Появится диалоговое окно **Свойства проекта**.  
  
3.  На вкладке **Общие** диалогового окна **Свойства проекта** измените имя проекта, введя `ComObject1` в поле **Название проекта**.  
  
4.  В **Обозревателе проекта** щелкните правой кнопкой мыши `Class1` и нажмите кнопку **Свойства**.  Появится окно **Свойства** для класса.  
  
5.  Измените свойство `Name` на `MathFunctions`.  
  
6.  В **Обозревателе проекта** щелкните `MathFunctions` правой кнопкой мыши и нажмите кнопку **Перейти к коду**.  Отображается **Редактор кода**.  
  
7.  Создайте локальную переменную для хранения значения свойства:  
  
    ```  
    ' Local variable to hold property value  
    Private mvarProp1 As Integer  
    ```  
  
8.  Добавьте процедуры свойства Property `Let` и Property `Get`:  
  
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
  
10. Создайте и зарегистрируйте объект COM, щелкнув **Создать ComObject1.dll** в меню **Файл**.  
  
    > [!NOTE]
    >  Хотя пользователь может предоставить класс, созданный в [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] как объект COM, он не является истинным объектом COM и не может быть использован в этом пошаговом руководстве.  Дополнительные сведения см. в разделе [COM\-взаимодействие в приложениях .NET Framework](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).  
  
## Сборки взаимодействия  
 В данной процедуре описано, как создать сборку взаимодействия, которая действует в качестве моста между неуправляемым кодом \(таким как объект COM\) и управляемым кодом, который использует [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)].  Созданная [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] сборка взаимодействия обеспечивает различные аспекты работы с COM\-объектами, например *маршалинг взаимодействия*, процесс упаковки параметров и возврат значений в эквивалентные типы данных при передаче COM\-объектам и получении из них.  Ссылка в приложении [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] обращается к сборке взаимодействия, а не к самому объекту COM.  
  
#### Использование COM\-объекта в Visual Basic 2005 и более поздних версиях  
  
1.  Откройте новый проект приложения Windows в [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  
  
2.  В меню **Проект** щелкните команду **Добавить ссылку**.  
  
     Появится диалоговое окно **Добавление ссылки**.  
  
3.  На вкладке **COM** дважды щелкните `ComObject1` в списке **Имя компонента** и нажмите кнопку **OK**.  
  
4.  В меню **Проект** выберите команду **Добавить новый элемент**.  
  
     Откроется диалоговое окно **Добавление нового элемента**.  
  
5.  В области **Шаблоны** щелкните **Класс**.  
  
     Имя файла по умолчанию — `Class1.vb` — отображается в поле **Имя**.  Измените значение поля на MathClass.vb и нажмите кнопку **Добавить**.  Создается класс с именем `MathClass`, а его код отображается на экране.  
  
6.  Добавьте следующий код в верхнюю часть `MathClass` для наследования от класса COM.  
  
     [!code-vb[VbVbalrInterop#31](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_1.vb)]  
  
7.  Перегрузите открытый метод базового класса, добавив следующий код к `MathClass`:  
  
     [!code-vb[VbVbalrInterop#32](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_2.vb)]  
  
8.  Расширьте наследуемый класс, добавив следующий код к `MathClass`:  
  
     [!code-vb[VbVbalrInterop#33](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_3.vb)]  
  
 Новый класс наследует свойства базового класса в объекте COM, перегружает метод и определяет новый метод для расширения класса.  
  
#### Чтобы проверить унаследованный класс  
  
1.  Добавьте кнопку на начальной форме, а затем дважды щелкните ее, чтобы просмотреть ее код.  
  
2.  В процедуре обработки события `Click` добавьте следующий код для создания экземпляра `MathClass` и вызовите перегруженные методы:  
  
     [!code-vb[VbVbalrInterop#34](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_4.vb)]  
  
3.  Запустите проект, нажав клавишу F5.  
  
 При нажатии кнопки на форме метод `AddNumbers` сначала вызывается с номерами типом данных `Short`, и [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] выбирает соответствующий метод из базового класса.  Второй вызов `AddNumbers` направляется в перегруженный метод из `MathClass`.  Третий вызов вызывает метод `SubtractNumbers`, который расширяет класс.  Задается свойство в базовом классе, и отображается значение.  
  
## Следующие действия  
 Обратите внимание на то, что перегруженная функция `AddNumbers` требует тот же тип данных, что и метод, унаследованный от базового класса COM\-объекта.  Причина в том, что в Visual Basic 6.0 аргументы и параметры метода базового класса определены как 16\-разрядные целые значения, а в последующих версиях Visual Basic они представлены как 16\-разрядные целые значения типа `Short`.  Новая функция поддерживает 32\-разрядные целые значения и перегружает функцию базового класса.  
  
 При работе с объектами COM убедитесь в правильности размера и типов данных параметров.  Например, при использовании объекта COM, который поддерживает объект коллекции Visual Basic 6.0 как аргумент, невозможно использовать коллекцию последней версии Visual Basic .NET.  
  
 Свойства и методы, унаследованные из классов COM, могут быть переопределены. Иными словами, можно объявить локальное свойство или метод, которые заменяют свойство или метод, унаследованные от базового класса COM.  Правила переопределения унаследованных свойств COM аналогичны правилам переопределения других свойств и методов со следующими исключениями:  
  
-   Если переопределяются унаследованные из класса COM свойства или методы, необходимо переопределить все остальные унаследованные свойства и методы.  
  
-   Свойства, использующие параметры `ByRef`, не могут быть переопределены.  
  
## См. также  
 [COM\-взаимодействие в приложениях .NET Framework](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)   
 [Инструкция Inherits](../../../visual-basic/language-reference/statements/inherits-statement.md)   
 [Тип данных Short](../../../visual-basic/language-reference/data-types/short-data-type.md)