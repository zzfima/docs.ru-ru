---
title: "Пошаговое руководство: Вызов Windows API (Visual Basic) | Документы Microsoft"
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
- DLLs, calling
- Windows API, walkthroughs
- platform invoke, walkthroughs
- API calls, walkthroughs [Visual Basic]
- Windows API, calling
- walkthroughs [Visual Basic], API calls
- DllImport attribute, calling Windows API
- Declare statement, declaring DLL functions
ms.assetid: 9280ca96-7a93-47a3-8d01-6d01be0657cb
caps.latest.revision: 20
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
ms.openlocfilehash: 5001ccebb0a5b8cadd4e856342601506cf1d033f
ms.lasthandoff: 03/13/2017

---
# <a name="walkthrough-calling-windows-apis-visual-basic"></a>Пошаговое руководство. Вызов API Windows (Visual Basic)
Интерфейсы Windows API являются библиотек динамической компоновки (DLL), которые являются частью операционной системы Windows. Они используются для выполнения задач, когда сложно написать собственную соответствующую процедуру. Например, в Windows есть функция с именем `FlashWindowEx` , позволяющая изменять строку заголовка приложения между светлые и темные оттенки.  
  
 Преимущество применения интерфейсов Windows API в коде — что они может сократить время разработки, так как они содержат множество полезных функций, которые уже записаны и ожидания для использования. Недостатком является то, что API-интерфейсов Windows может быть трудно работать с и они не допускают при неправильном.  
  
 Интерфейсы Windows API представляют собой специальную категорию взаимодействия. Интерфейсы Windows API не используют управляемый код, не имеют встроенных библиотек и используют типы данных, отличные от тех, которые используются в Visual Studio. Из-за этих различий и потому, что интерфейсы Windows API не являются объектами COM, взаимодействие с интерфейсами API Windows и [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] выполняется с помощью вызова неуправляемого кода, или PInvoke. Вызов неуправляемого кода — это служба, позволяющая управляемому коду вызывать неуправляемые функции, реализованные в библиотеках DLL. Дополнительные сведения см. в разделе [использование неуправляемых функций DLL](http://msdn.microsoft.com/library/eca7606e-ebfb-4f47-b8d9-289903fdc045). Можно использовать PInvoke в [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] с помощью `Declare` инструкции или применение `DllImport` атрибут к пустой процедуре.  
  
 Вызовы Windows API были важной частью [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] программирование в прошлом, но редко бывают необходимости [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)]. По возможности следует использовать управляемый код из [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] для выполнения задач, а не вызовы Windows API. Это пошаговое руководство содержит сведения для ситуаций, в которых использование API-интерфейсов Windows не требуется.  
  
[!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
## <a name="api-calls-using-declare"></a>Вызовы API с помощью объявления  
 Наиболее распространенный способ вызова интерфейса Windows API — с помощью `Declare` инструкции.  
  
#### <a name="to-declare-a-dll-procedure"></a>Объявление процедуры DLL  
  
1.  Определите имя функции, которую необходимо вызвать, ее аргументы, типы аргументов и возвращают значение, а также имя и расположение библиотеки DLL, которая его содержит.  
  
    > [!NOTE]
    >  Полные сведения о функции Windows API см. в документации Win32 SDK в Platform SDK Windows API. Дополнительные сведения о константах, используемых Windows API просмотрите файлы заголовков, такие как Windows.h, входящий в состав пакета Platform SDK.  
  
2.  Откройте новый проект приложения Windows, щелкнув **New** на **файл** , а затем выберите **проекта**. Откроется диалоговое окно **Новый проект** .  
  
3.  Выберите **приложения Windows** из списка [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] шаблонов проектов. Откроется новый проект.  
  
4.  Добавьте следующие `Declare` работать либо в класс или модуль, в котором требуется использование DLL:  
  
     [!code-vb[VbVbalrInterop №&9;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_1.vb)]  
  
### <a name="parts-of-the-declare-statement"></a>Части оператор Declare  
 `Declare` Инструкция включает в себя следующие элементы.  
  
#### <a name="auto-modifier"></a>Модификатор Auto  
 `Auto` Модификатор инструктирует среду выполнения о необходимости преобразования строки на основе имени метода в соответствии с общих правил языка среды выполнения (или псевдоним, если указан).  
  
#### <a name="lib-and-alias-keywords"></a>Ключевые слова lib и псевдоним  
 Следующее имя `Function` ключевое слово — это имя, программа использует для доступа к импортируемой функции. Он может совпадать с реальным именем вызываемой функции, или можно использовать любое недопустимое имя процедуры и затем используют `Alias` слово настоящее имя вызываемой функции.  
  
 Укажите `Lib` ключевое слово, и имя и расположение библиотеки DLL, которая содержит вызываемой функции. Необходимо указать путь для файлов, расположенных в каталогах системы Windows.  
  
 Используйте `Alias` ключевое слово, если имя вызываемой функции не является допустимым [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] имя процедуры или конфликтует с именем других элементов в приложении. `Alias`Указывает правильное имя вызываемой функции.  
  
#### <a name="argument-and-data-type-declarations"></a>Аргумент и объявления типов данных  
 Объявите аргументы и их типы данных. Эта часть может оказаться сложной задачей, поскольку типы данных, которые использует Windows не соответствуют типам данных Visual Studio. [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]выполняет большой объем работы за разработчика, преобразуя аргументы в совместимые типы данных, процесс, называемый *маршалинг*. Можно явным образом управлять маршалингом аргументов с помощью <xref:System.Runtime.InteropServices.MarshalAsAttribute>атрибуту, определенному в <xref:System.Runtime.InteropServices>имен.</xref:System.Runtime.InteropServices> </xref:System.Runtime.InteropServices.MarshalAsAttribute>  
  
> [!NOTE]
>  Предыдущие версии [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] может объявлять параметры `As Any`, это означает, что данные любого типа могут использоваться. [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]необходимо использовать определенный тип данных для всех `Declare` инструкции.  
  
#### <a name="windows-api-constants"></a>Константы Windows API  
 Некоторые аргументы являются сочетаниями констант. Например `MessageBox` API, приведенных в этом руководстве принимает целочисленный аргумент под названием `Typ` , определяет, как отображается в окне сообщения. Можно определить числовое значение этих констант, изучив `#define` инструкций в файле WinUser.h. Числовые значения обычно отображаются в шестнадцатеричном формате, поэтому можно воспользоваться калькулятором для их сложения и преобразования в десятичное. Например, если требуется объединить константы стиля восклицания `MB_ICONEXCLAMATION` 0x00000030 и Да/Нет стиля `MB_YESNO` 0x00000004, можно сложить эти числа и получить результат 0x00000034, или 52 десятичное число. Несмотря на то, что можно использовать непосредственно десятичное число, лучше объявить эти значения в приложении как константы и сочетать их с помощью `Or` оператор.  
  
###### <a name="to-declare-constants-for-windows-api-calls"></a>Объявление констант для вызовов интерфейса Windows API  
  
1.  Обратитесь к документации для вызываемой функции Windows. Определите имя константы, которую она использует и имя h-файл, содержащий числовые значения для этих констант.  
  
2.  Используйте текстовый редактор, например Блокнот, чтобы просмотреть содержимое файла заголовка (h) и найти значения, связанные с константы, которые вы используете. Например `MessageBox` API использует константу `MB_ICONQUESTION` чтобы показать знак вопроса в окне сообщения. Определение `MB_ICONQUESTION` в WinUser.h и выглядит следующим образом:  
  
     `#define MB_ICONQUESTION             0x00000020L`  
  
3.  Добавьте соответствующие `Const` инструкций в ваш класс или модуль, чтобы сделать эти константы доступными для приложения. Пример:  
  
     [!code-vb[VbVbalrInterop&11;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_2.vb)]  
  
###### <a name="to-call-the-dll-procedure"></a>Вызов процедуры DLL  
  
1.  Добавьте кнопку с именем `Button1` для запуска формы для проекта и дважды щелкните его для просмотра его кода. Обработчик событий для кнопки отображается.  
  
2.  Добавьте код для `Click` обработчик событий для кнопки, который был добавлен, чтобы вызвать процедуру и предоставьте соответствующие аргументы:  
  
     [!code-vb[VbVbalrInterop&#12;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_3.vb)]  
  
3.  Запустите проект, нажав клавишу F5. Отображает окно сообщения с обоих **Да** и **нет** кнопками. Нажмите одну из них.  
  
#### <a name="data-marshaling"></a>Маршалинг данных  
 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]автоматически преобразует типы данных параметров и возвращаемых значений вызовов интерфейса Windows API, но можно использовать `MarshalAs` атрибут, чтобы явно указать неуправляемые типы данных, ожидаемые интерфейсом API. Дополнительные сведения о маршалинге взаимодействия см. в разделе [маршалинг взаимодействия](http://msdn.microsoft.com/library/115f7a2f-d422-4605-ab36-13a8dd28142a).  
  
###### <a name="to-use-declare-and-marshalas-in-an-api-call"></a>Для использования в вызове API Declare и MarshalAs  
  
1.  Определите имя функции, необходимо вызвать, ее аргументы, типы данных и возвращаемое значение.  
  
2.  Чтобы упростить доступ к `MarshalAs` атрибута, добавьте `Imports` инструкции в начало класса или модуля, как показано в следующем примере кода:  
  
     [!code-vb[VbVbalrInterop&#13;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_4.vb)]  
  
3.  Добавьте прототип функции для импортированной функции в класс или модуль, вы используете и применить `MarshalAs` атрибут параметры или возвращаемое значение. В следующем примере вызов API, который ожидает тип `void*` маршалируется как `AsAny`:  
  
     [!code-vb[VbVbalrInterop&#14;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_5.vb)]  
  
## <a name="api-calls-using-dllimport"></a>Вызовы API, с помощью DllImport  
 `DllImport` Атрибут содержит второй способ вызова функций в DLL без библиотек типов. `DllImport`с помощью примерно соответствует `Declare` инструкции, но обеспечивает больший контроль над процессом вызова функций.  
  
 Можно использовать `DllImport` с большинством API Windows вызывает при условии, что вызов связан общий (иногда называется *статического*) метод. Нельзя использовать методы, которым требуется экземпляр класса. В отличие от `Declare` инструкций, `DllImport` вызовы нельзя использовать `MarshalAs` атрибута.  
  
#### <a name="to-call-a-windows-api-using-the-dllimport-attribute"></a>Для вызова API Windows, используя атрибут DllImport  
  
1.  Откройте новый проект приложения Windows, щелкнув **New** на **файл** , а затем выберите **проекта**. Откроется диалоговое окно **Новый проект** .  
  
2.  Выберите **приложения Windows** из списка [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] шаблонов проектов. Откроется новый проект.  
  
3.  Добавьте кнопку с именем `Button2` форму запуска.  
  
4.  Дважды щелкните `Button2` чтобы открыть представление кода для формы.  
  
5.  Чтобы упростить доступ к `DllImport`, добавьте `Imports` инструкции в начало кода класса формы запуска:  
  
     [!code-vb[VbVbalrInterop&#13;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_4.vb)]  
  
6.  Объявите пустую функцию выше `End Class` инструкции для формы и имя функции `MoveFile`.  
  
7.  Применить `Public` и `Shared` модификаторы объявления функции и задать параметры для `MoveFile` на основе аргументов, использует функции Windows API:  
  
     [!code-vb[VbVbalrInterop №&16;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_6.vb)]  
  
     Функция может иметь любое допустимое имя процедуры; `DllImport` атрибут указывает имя библиотеки DLL. Он также управляет маршалингом взаимодействия для параметров и возвращаемых значений, поэтому можно выбрать типы данных Visual Studio, которые похожи на данные типы использует API.  
  
8.  Применить `DllImport` атрибута пустой функции. Первый параметр — имя и расположение библиотеки DLL, содержащей функцию, который вы вызываете. Необходимо указать путь для файлов, расположенных в каталогах системы Windows. Второй параметр — именованный аргумент, который задает имя функции в Windows API. В этом примере `DllImport` атрибут приводит вызовы `MoveFile` пересылать `MoveFileW` в KERNEL32. БИБЛИОТЕКА DLL. `MoveFileW` Метод копирует файл из пути `src` путь `dst`.  
  
     [!code-vb[VbVbalrInterop&17;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_7.vb)]  
  
9. Добавьте код для `Button2_Click` обработчик событий для вызова функции:  
  
     [!code-vb[VbVbalrInterop&18;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_8.vb)]  
  
10. Создайте файл с именем Test.txt и поместите его в каталог C:\Tmp на жестком диске. При необходимости создайте каталог Tmp.  
  
11. Нажмите клавишу F5 для запуска приложения. Появится главная форма.  
  
12. Щелкните **Button2**. Сообщение «файл был перемещен успешно» отображается в том случае, если файл можно переместить.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Runtime.InteropServices.DllImportAttribute></xref:System.Runtime.InteropServices.DllImportAttribute>   
 <xref:System.Runtime.InteropServices.MarshalAsAttribute></xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md)   
 [Авто](../../../visual-basic/language-reference/modifiers/auto.md)   
 [Псевдоним](../../../visual-basic/language-reference/statements/alias-clause.md)   
 [Взаимодействие COM](../../../visual-basic/programming-guide/com-interop/index.md)   
 [Создание прототипов в управляемом коде](http://msdn.microsoft.com/library/ecdcf25d-cae3-4f07-a2b6-8397ac6dc42d)   
 [Маршалинг делегата как метода обратного вызова](http://msdn.microsoft.com/library/6ddd7866-9804-4571-84de-83f5cc017a5a)
