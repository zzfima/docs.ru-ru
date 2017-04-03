---
title: "Пошаговое руководство. Создание и использование динамических объектов (C# и Visual Basic) | Документы Майкрософт"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- dynamic objects [Visual Basic]
- dynamic objects
- dynamic objects [C#]
ms.assetid: 568f1645-1305-4906-8625-5d77af81e04f
caps.latest.revision: 22
author: BillWagner
ms.author: wiwagn
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
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 64f6354a6a5f2fdd078e7ae9a1bfafc65d53373d
ms.lasthandoff: 03/13/2017

---
# <a name="walkthrough-creating-and-using-dynamic-objects-c-and-visual-basic"></a>Пошаговое руководство. Создание и использование динамических объектов (C# и Visual Basic)
Динамические объекты предоставляют такие элементы, как свойства и методы, во время выполнения, а не во время компиляции. Это позволяет создавать объекты для работы со структурами, не соответствующими статическому типу или формату. Например, можно использовать динамический объект для ссылки на модель DOM HTML, которая может содержать любую комбинацию допустимых элементов и атрибутов разметки HTML. Поскольку каждый документ HTML является уникальным, элементы для конкретного документа HTML определяются во время выполнения. Наиболее распространенный способ ссылки на атрибут элемента HTML заключается в передаче имени этого атрибута в метод `GetProperty` элемента. Для ссылки на атрибут `id` элемента HTML `<div id="Div1">` следует сначала получить ссылку на элемент `<div>`, а затем использовать `divElement.GetProperty("id")`. При использовании динамического объекта можно сослаться на атрибут `id` в виде `divElement.id`.  
  
 Динамические объекты обеспечивают удобный доступ к динамическим языкам, таким как IronPython и IronRuby. С помощью динамического объекта можно ссылаться на динамический скрипт, интерпретируемый во время выполнения.  
  
 Ссылка на динамический объект выполняется с помощью позднего связывания. В C# тип объектов с поздним связыванием указывается как `dynamic`. В [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] тип объектов с поздним связыванием указывается как `Object`. Дополнительные сведения см. в разделах [dynamic](../../../csharp/language-reference/keywords/dynamic.md) и [Раннее и позднее связывание](../../../visual-basic/programming-guide/language-features/early-late-binding/index.md).  
  
 Существует возможность создания пользовательских динамических объектов с помощью классов в пространстве имен <xref:System.Dynamic?displayProperty=fullName>. Например, можно создать объект <xref:System.Dynamic.ExpandoObject> и задать элементы этого объекта во время выполнения. Можно также создать собственный тип, наследующий класс <xref:System.Dynamic.DynamicObject>. Затем для обеспечения динамических функциональных возможностей во время выполнения можно переопределить элементы класса <xref:System.Dynamic.DynamicObject>.  
  
 В данном пошаговом руководстве демонстрируется выполнение следующих задач:  
  
-   Создание пользовательского объекта, который динамически предоставляет содержимое текстового файла в виде свойств объекта.  
  
-   Создание проекта, использующего библиотеку `IronPython`.  
  
## <a name="prerequisites"></a>Предварительные требования  
 Для выполнения инструкций этого пошагового руководства потребуется установить IronPython 2.6.1 для .NET 4.0. IronPython 2.6.1 для .NET 4.0 можно скачать со страницы [CodePlex](http://go.microsoft.com/fwlink/?LinkId=187223).  
  
[!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
## <a name="creating-a-custom-dynamic-object"></a>Создание пользовательского динамического объекта  
 В первом проекте, создаваемом в данном пошаговом руководстве, определяется пользовательский динамический объект, выполняющий поиск по содержимому текстового файла. Текст для поиска задается именем динамического свойства. Например, если в вызывающем коде указано `dynamicFile.Sample`, динамический класс возвращает общий список строк, содержащий все строки из файла, которые начинаются со слова "Sample". При поиске не учитывается регистр. Динамический класс также поддерживает два дополнительных аргумента. Первый аргумент — это значение перечисления параметра поиска, задающее, где динамический класс должен искать соответствия: в начале строки, в конце строки или в любом месте строки. Второй аргумент задает, что динамический класс должен перед поиском отсекать начальные и конечные пробелы в каждой строке. Например, если в вызывающем коде указано `dynamicFile.Sample(StringSearchOption.Contains)`, динамический класс выполняет поиск слова "Sample" в любом месте строки. Если в вызывающем коде указано `dynamicFile.Sample(StringSearchOption.StartsWith, false)`, динамический класс выполняет поиск слова "Sample" в начале каждой строки и не удаляет начальные и конечные пробелы в строках. По умолчанию динамический класс выполняет поиск соответствия в начале каждой строки, предварительно удаляя начальные и конечные пробелы.  
  
#### <a name="to-create-a-custom-dynamic-class"></a>Создание пользовательского динамического класса  
  
1.  Запустите [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)].  
  
2.  В меню **Файл** выберите пункт **Создать** , а затем команду **Проект**.  
  
3.  Убедитесь, что в диалоговом окне **Создание проекта** в области **Типы проектов** выбран пункт **Windows**. В области **Шаблоны** выберите пункт **Консольное приложение**. В поле **Имя** введите `DynamicSample` и нажмите кнопку **ОК**. Проект создан.  
  
4.  Щелкните правой кнопкой мыши проект DynamicSample, выберите пункт **Добавить**, а затем щелкните **Класс**. В поле **Имя** введите `ReadOnlyFile` и нажмите кнопку **ОК**. Будет добавлен новый файл, содержащий класс ReadOnlyFile.  
  
5.  В верхней части файла ReadOnlyFile.cs или ReadOnlyFile.vb добавьте следующий код для импорта пространств имен <xref:System.IO?displayProperty=fullName> и <xref:System.Dynamic?displayProperty=fullName>.  
  
     [!code-cs[VbDynamicWalkthrough#1](../../../csharp/programming-guide/types/codesnippet/CSharp/walkthrough-creating-and-using-dynamic-objects_1.cs)]
     [!code-vb[VbDynamicWalkthrough#1](../../../csharp/programming-guide/types/codesnippet/VisualBasic/walkthrough-creating-and-using-dynamic-objects_1.vb)]  
  
6.  Пользовательский динамический объект использует перечисление для определения условия поиска. Перед оператором класса добавьте следующее определение перечисления.  
  
     [!code-cs[VbDynamicWalkthrough#2](../../../csharp/programming-guide/types/codesnippet/CSharp/walkthrough-creating-and-using-dynamic-objects_2.cs)]
     [!code-vb[VbDynamicWalkthrough#2](../../../csharp/programming-guide/types/codesnippet/VisualBasic/walkthrough-creating-and-using-dynamic-objects_2.vb)]  
  
7.  Обновите оператор класса, чтобы он наследовал класс `DynamicObject`, как показано в следующем примере кода.  
  
     [!code-cs[VbDynamicWalkthrough#3](../../../csharp/programming-guide/types/codesnippet/CSharp/walkthrough-creating-and-using-dynamic-objects_3.cs)]
     [!code-vb[VbDynamicWalkthrough#3](../../../csharp/programming-guide/types/codesnippet/VisualBasic/walkthrough-creating-and-using-dynamic-objects_3.vb)]  
  
8.  Добавьте в класс `ReadOnlyFile` следующий код, чтобы задать закрытое поле для пути к файлу и конструктор для класса `ReadOnlyFile`.  
  
     [!code-cs[VbDynamicWalkthrough#4](../../../csharp/programming-guide/types/codesnippet/CSharp/walkthrough-creating-and-using-dynamic-objects_4.cs)]
     [!code-vb[VbDynamicWalkthrough#4](../../../csharp/programming-guide/types/codesnippet/VisualBasic/walkthrough-creating-and-using-dynamic-objects_4.vb)]  
  
9. Добавьте следующий метод `GetPropertyValue` в класс `ReadOnlyFile`. Метод `GetPropertyValue` принимает в качестве входных данных условие поиска и возвращает строки текстового файла, соответствующие этому условию. Динамический метод, предоставленный классом `ReadOnlyFile`, вызывает метод `GetPropertyValue` для извлечения соответствующих результатов.  
  
     [!code-cs[VbDynamicWalkthrough#5](../../../csharp/programming-guide/types/codesnippet/CSharp/walkthrough-creating-and-using-dynamic-objects_5.cs)]
     [!code-vb[VbDynamicWalkthrough#5](../../../csharp/programming-guide/types/codesnippet/VisualBasic/walkthrough-creating-and-using-dynamic-objects_5.vb)]  
  
10. После метода `GetPropertyValue` добавьте следующий код, чтобы переопределить метод <xref:System.Dynamic.DynamicObject.TryGetMember%2A> класса <xref:System.Dynamic.DynamicObject>. Метод <xref:System.Dynamic.DynamicObject.TryGetMember%2A> вызывается при запросе элемента динамического класса без указания аргументов. Аргумент `binder` содержит сведения об элементе, на который дается ссылка, а аргумент `result` ссылается на результат, возвращенный для указанного элемента. Метод <xref:System.Dynamic.DynamicObject.TryGetMember%2A> возвращает логическое значение `true`, если запрошенный элемент существует. В противном случае возвращается `false`.  
  
     [!code-cs[VbDynamicWalkthrough#6](../../../csharp/programming-guide/types/codesnippet/CSharp/walkthrough-creating-and-using-dynamic-objects_6.cs)]
     [!code-vb[VbDynamicWalkthrough#6](../../../csharp/programming-guide/types/codesnippet/VisualBasic/walkthrough-creating-and-using-dynamic-objects_6.vb)]  
  
11. После метода `TryGetMember` добавьте следующий код, чтобы переопределить метод <xref:System.Dynamic.DynamicObject.TryInvokeMember%2A> класса <xref:System.Dynamic.DynamicObject>. Метод <xref:System.Dynamic.DynamicObject.TryInvokeMember%2A> вызывается при запросе элемента динамического класса c аргументами. Аргумент `binder` содержит сведения об элементе, на который дается ссылка, а аргумент `result` ссылается на результат, возвращенный для указанного элемента. Аргумент `args` содержит массив аргументов, передаваемых в элемент. Метод <xref:System.Dynamic.DynamicObject.TryInvokeMember%2A> возвращает логическое значение `true`, если запрошенный элемент существует. В противном случае возвращается `false`.  
  
     Пользовательская версия метода `TryInvokeMember` ожидает, что первый аргумент будет значением из перечисления `StringSearchOption`, заданного на предыдущем шаге. Метод `TryInvokeMember` ожидает, что второй аргумент будет логическим значением. Если один или оба элемента имеют допустимые значения, они передаются в метод `GetPropertyValue` для получения результатов.  
  
     [!code-cs[VbDynamicWalkthrough#7](../../../csharp/programming-guide/types/codesnippet/CSharp/walkthrough-creating-and-using-dynamic-objects_7.cs)]
     [!code-vb[VbDynamicWalkthrough#7](../../../csharp/programming-guide/types/codesnippet/VisualBasic/walkthrough-creating-and-using-dynamic-objects_7.vb)]  
  
12. Сохраните и закройте файл.  
  
#### <a name="to-create-a-sample-text-file"></a>Создание примера текстового файла  
  
1.  Щелкните правой кнопкой мыши проект DynamicSample, выберите пункт **Добавить**, а затем щелкните **Новый элемент**. На панели **Установленные шаблоны** выберите **Общие**, а затем шаблон **Текстовый файл**. В поле **Имя** оставьте имя по умолчанию TextFile1.txt и нажмите кнопку **Добавить**. В проект добавится новый текстовый файл.  
  
2.  Скопируйте в файл TextFile1.txt следующий текст.  
  
    ```  
    List of customers and suppliers  
  
    Supplier: Lucerne Publishing (http://www.lucernepublishing.com/)  
    Customer: Preston, Chris  
    Customer: Hines, Patrick  
    Customer: Cameron, Maria  
    Supplier: Graphic Design Institute (http://www.graphicdesigninstitute.com/)   
    Supplier: Fabrikam, Inc. (http://www.fabrikam.com/)   
    Customer: Seubert, Roxanne  
    Supplier: Proseware, Inc. (http://www.proseware.com/)   
    Customer: Adolphi, Stephan  
    Customer: Koch, Paul  
    ```  
  
3.  Сохраните и закройте файл.  
  
#### <a name="to-create-a-sample-application-that-uses-the-custom-dynamic-object"></a>Создание примера приложения, в котором применяется пользовательский динамический объект  
  
1.  В **обозревателе решений** дважды щелкните файл Module1.vb, если используется [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], или файл Program.cs, если используется Visual C#.  
  
2.  Добавьте следующий код в процедуру Main, чтобы создать экземпляр класса `ReadOnlyFile` для файла TextFile1.txt. В этом коде используется позднее связывание для вызова динамических элементов и извлечения строк текста, которые содержат строку "Customer".  
  
     [!code-cs[VbDynamicWalkthrough#8](../../../csharp/programming-guide/types/codesnippet/CSharp/walkthrough-creating-and-using-dynamic-objects_8.cs)]
     [!code-vb[VbDynamicWalkthrough#8](../../../csharp/programming-guide/types/codesnippet/VisualBasic/walkthrough-creating-and-using-dynamic-objects_8.vb)]  
  
3.  Сохраните файл и нажмите сочетание клавиш CTRL+F5 для сборки и запуска приложения.  
  
## <a name="calling-a-dynamic-language-library"></a>Вызов библиотеки динамического языка  
 В следующем проекте, создаваемом в ходе данного пошагового руководства, осуществляется доступ к библиотеке, написанной на динамическом языке IronPython. Перед созданием этого проекта необходимо установить IronPython 2.6.1 для .NET 4.0. IronPython 2.6.1 для .NET 4.0 можно скачать со страницы [CodePlex](http://go.microsoft.com/fwlink/?LinkId=187223).  
  
#### <a name="to-create-a-custom-dynamic-class"></a>Создание пользовательского динамического класса  
  
1.  В [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] в меню **Файл** последовательно выберите пункты **Создать**, **Проект**.  
  
2.  Убедитесь, что в диалоговом окне **Создание проекта** в области **Типы проектов** выбран пункт **Windows**. В области **Шаблоны** выберите пункт **Консольное приложение**. В поле **Имя** введите `DynamicIronPythonSample` и нажмите кнопку **ОК**. Проект создан.  
  
3.  Если используется [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], щелкните правой кнопкой мыши проект DynamicIronPythonSample и выберите пункт **Свойства**. Перейдите на вкладку **Ссылки**. Нажмите кнопку **Добавить**. Если используется Visual C#, в **обозревателе решений** щелкните правой кнопкой мыши папку **Ссылки** и выберите пункт **Добавить ссылку**.  
  
4.  На вкладке **Обзор** перейдите к папке, в которой установлены библиотеки IronPython. Например, C:\Program Files\IronPython 2.6 for .NET 4.0. Выберите библиотеки **IronPython.dll**, **IronPython.Modules.dll**, **Microsoft.Scripting.dll** и **Microsoft.Dynamic.dll**. Нажмите кнопку **ОК**.  
  
5.  Если используется [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], отредактируйте файл Module1.vb. Если используется Visual C#, отредактируйте файл Program.cs.  
  
6.  В верхней части файла добавьте следующий код для импорта пространств имен `Microsoft.Scripting.Hosting` и `IronPython.Hosting` из библиотек IronPython.  
  
     [!code-cs[VbDynamicWalkthroughIronPython#1](../../../csharp/programming-guide/types/codesnippet/CSharp/walkthrough-creating-and-using-dynamic-objects_9.cs)]
     [!code-vb[VbDynamicWalkthroughIronPython#1](../../../csharp/programming-guide/types/codesnippet/VisualBasic/walkthrough-creating-and-using-dynamic-objects_9.vb)]  
  
7.  В методе Main добавьте следующий код, чтобы создать объект `Microsoft.Scripting.Hosting.ScriptRuntime`, в котором будут размещены библиотеки IronPython. Объект `ScriptRuntime` загружает модуль библиотеки IronPython random.py.  
  
     [!code-cs[VbDynamicWalkthroughIronPython#2](../../../csharp/programming-guide/types/codesnippet/CSharp/walkthrough-creating-and-using-dynamic-objects_10.cs)]
     [!code-vb[VbDynamicWalkthroughIronPython#2](../../../csharp/programming-guide/types/codesnippet/VisualBasic/walkthrough-creating-and-using-dynamic-objects_10.vb)]  
  
8.  После указания в коде необходимости загрузки модуля random.py добавьте следующий код, чтобы создать массив целых чисел. Массив передается методу `shuffle` модуля random.py, который произвольно сортирует значения в массиве.  
  
     [!code-cs[VbDynamicWalkthroughIronPython#3](../../../csharp/programming-guide/types/codesnippet/CSharp/walkthrough-creating-and-using-dynamic-objects_11.cs)]
     [!code-vb[VbDynamicWalkthroughIronPython#3](../../../csharp/programming-guide/types/codesnippet/VisualBasic/walkthrough-creating-and-using-dynamic-objects_11.vb)]  
  
9. Сохраните файл и нажмите сочетание клавиш CTRL+F5 для сборки и запуска приложения.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Dynamic?displayProperty=fullName>   
 <xref:System.Dynamic.DynamicObject?displayProperty=fullName>   
 [Использование типа dynamic](../../../csharp/programming-guide/types/using-type-dynamic.md)   
 [Раннее и позднее связывание](../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)   
 [dynamic](../../../csharp/language-reference/keywords/dynamic.md)   
 [Реализация динамических интерфейсов (внешний блог)](http://go.microsoft.com/fwlink/?LinkId=230895)
