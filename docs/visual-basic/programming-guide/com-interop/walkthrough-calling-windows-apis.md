---
title: Пошаговое руководство. Вызов API Windows (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- DLLs, calling
- Windows API, walkthroughs
- platform invoke, walkthroughs
- API calls [Visual Basic], walkthroughs [Visual Basic]
- Windows API, calling
- walkthroughs [Visual Basic], API calls
- DllImport attribute, calling Windows API
- Declare statement [Visual Basic], declaring DLL functions
ms.assetid: 9280ca96-7a93-47a3-8d01-6d01be0657cb
ms.openlocfilehash: bb98d842bfe65bdf637a789fc9a8319a70cb2bc8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33644359"
---
# <a name="walkthrough-calling-windows-apis-visual-basic"></a>Пошаговое руководство. Вызов API Windows (Visual Basic)
API-интерфейсов Windows являются библиотек динамической компоновки (DLL), которые являются частью операционной системы Windows. Вы используете их для выполнения задач, когда сложно написать собственную соответствующую процедуру. Например, в Windows есть функция с именем `FlashWindowEx` , позволяющий изменять строку заголовка приложения от светлые и темные оттенки.  
  
 Преимущество использования API-интерфейсов Windows в коде является, это может сократить время разработки, так как они содержат множество полезных функций, которые уже записаны и ожидания для использования. Недостатком является то, что API-интерфейсов Windows может быть трудно работать с и не реагирует на возникающие проблемы.  
  
 API-интерфейсы Windows представляют собой специальную категорию взаимодействия. API-интерфейсы Windows не используют управляемый код, не имеют встроенных библиотек и использовать типы данных, которые отличаются от тех, которые используются вместе с Visual Studio. Из-за этих различий а потому, что Windows API не являются объектами COM, взаимодействие с API-интерфейсов Windows и [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] выполняется с помощью платформы неуправляемого кода, или PInvoke. Неуправляемого кода — это служба, позволяющая управляемому коду вызывать неуправляемые функции, реализованные в библиотеках DLL. Дополнительные сведения см. в разделе [использование неуправляемых функций DLL](../../../framework/interop/consuming-unmanaged-dll-functions.md). Можно использовать PInvoke в Visual Basic с помощью `Declare` инструкции или применения `DllImport` атрибут к пустой процедуре.  
  
 Вызовы Windows API были важной частью процесса программирования в прошлом Visual Basic, но редко необходимы в Visual Basic .NET. По возможности следует использовать управляемый код из [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] для выполнения задач, а не вызовы Windows API. Это пошаговое руководство содержит сведения для ситуаций, в которых с помощью API-интерфейсов Windows не требуется.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="api-calls-using-declare"></a>Вызовы API с помощью объявления  
 Самый распространенный способ вызова интерфейса Windows API — с помощью `Declare` инструкции.  
  
#### <a name="to-declare-a-dll-procedure"></a>Объявление процедуры DLL  
  
1.  Определить имя функции, в которую вы хотите вызвать, ее аргументы, типы аргументов и возвращают значение, а также имя и расположение библиотеки DLL, которая его содержит.  
  
    > [!NOTE]
    >  Полные сведения о API-интерфейсов Windows см. в документации Win32 SDK в Windows API пакета SDK для платформы. Дополнительные сведения о константах, используемых Windows API просмотрите файлы заголовков, такие как Windows.h, входящий в состав пакета Platform SDK.  
  
2.  Откройте новый проект приложения Windows, щелкнув **New** на **файл** меню и выбрав **проекта**. Откроется диалоговое окно **Новый проект** .  
  
3.  Выберите **приложение Windows** в списке шаблонов проектов Visual Basic. Откроется новый проект.  
  
4.  Добавьте следующие `Declare` работать либо в класс или модуль, в котором вы хотите использовать библиотеку DLL:  
  
     [!code-vb[VbVbalrInterop#9](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_1.vb)]  
  
### <a name="parts-of-the-declare-statement"></a>Части Declare-оператор  
 `Declare` Инструкция включает в себя следующие элементы.  
  
#### <a name="auto-modifier"></a>Модификатор Auto  
 `Auto` Модификатор выдает среде выполнения для преобразования строки на основе имени метода в соответствии с общие правила среды выполнения языка (или псевдоним, если указан).  
  
#### <a name="lib-and-alias-keywords"></a>Ключевые слова lib и псевдоним  
 Следующее имя `Function` ключевое слово — это имя, программа использует для доступа к импортированной функции. Он может совпадать с действительное имя вызываемой функции, или можно использовать любые недопустимое имя процедуры и затем используют `Alias` ключевое слово, чтобы указать действительное имя вызываемой функции.  
  
 Укажите `Lib` ключевое слово, за которым следует имя и расположение библиотеки DLL, которая содержит вызываемой функции. Необходимо указать путь к файлам, находящимся в системных каталогах Windows.  
  
 Используйте `Alias` ключевое слово, если вызов имя функции не является допустимым именем процедуры Visual Basic, или конфликтует с именем других элементов в приложении. `Alias` Указывает правильное имя вызываемой функции.  
  
#### <a name="argument-and-data-type-declarations"></a>Аргумент и объявления типов данных  
 Объявите аргументы и их типы данных. Эта часть может оказаться сложной задачей, так как типы данных, используемые Windows не соответствуют типам данных Visual Studio. Visual Basic выполняет большой объем работы за разработчика, преобразуя аргументы в совместимые типы данных, этот процесс называется *маршалинг*. Можно явным образом управлять маршалингом аргументов с помощью <xref:System.Runtime.InteropServices.MarshalAsAttribute> атрибуту, определенному в <xref:System.Runtime.InteropServices> пространства имен.  
  
> [!NOTE]
>  Предыдущие версии Visual Basic допускается объявлять параметры `As Any`, это означает, что данные любого типа могут использоваться. Visual Basic необходимо использовать определенный тип данных для всех `Declare` инструкции.  
  
#### <a name="windows-api-constants"></a>Константы Windows API  
 Некоторые аргументы являются сочетаниями констант. Например `MessageBox` API, приведенных в этом руководстве принимает целочисленный аргумент с именем `Typ` , определяет, как отображается в окне сообщения. Определите числовое значение этих констант, изучив `#define` инструкции в файле WinUser.h. Числовые значения обычно отображаются в шестнадцатеричном формате, поэтому можно использовать «калькулятор» для добавления их и преобразовать в десятичное. Например, если нужно объединить константы стиля восклицания `MB_ICONEXCLAMATION` 0x00000030 и Да/стиль не `MB_YESNO` 0x00000004, можно добавить номера и получить результат 0x00000034, или 52 десятичное число. Несмотря на то, что можно использовать непосредственно десятичное число, рекомендуется объявить эти значения в приложении как константы и объединить их с помощью `Or` оператор.  
  
###### <a name="to-declare-constants-for-windows-api-calls"></a>Объявление констант для вызовов Windows API  
  
1.  Обратитесь к документации для вызываемой функции Windows. Определите имя константы, используемые в нем и имя h-файл, содержащий числовые значения для этих констант.  
  
2.  Используйте текстовый редактор, например Блокнот, чтобы просмотреть содержимое файла заголовка (.h) и найти значения, связанные с константы, которые вы используете. Например `MessageBox` использует API константа `MB_ICONQUESTION` для отображения знак вопроса в окне сообщения. Определение `MB_ICONQUESTION` в WinUser.h и выглядит следующим образом:  
  
     `#define MB_ICONQUESTION             0x00000020L`  
  
3.  Добавьте соответствующие `Const` инструкции, чтобы класс или модуль, чтобы сделать эти константы доступными для приложения. Пример:  
  
     [!code-vb[VbVbalrInterop#11](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_2.vb)]  
  
###### <a name="to-call-the-dll-procedure"></a>Вызов процедуры DLL  
  
1.  Добавьте кнопку с именем `Button1` запуска форму для проекта и дважды щелкните его, чтобы увидеть ее код. Обработчик событий для кнопки отображается.  
  
2.  Добавьте код для `Click` обработчик событий для кнопки, которые вы добавили, чтобы вызвать процедуру и предоставьте соответствующие аргументы:  
  
     [!code-vb[VbVbalrInterop#12](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_3.vb)]  
  
3.  Запустите проект, нажав клавишу F5. Появляется окно сообщения с обоими **Да** и **нет** кнопками. Нажмите одну из них.  
  
#### <a name="data-marshaling"></a>Маршалинг данных  
 Visual Basic автоматически преобразует типы данных параметров и возвращаемых значений функций Windows API, но можно использовать `MarshalAs` атрибут, чтобы явно задать неуправляемые типы данных, ожидаемые интерфейсом API. Дополнительные сведения о маршалинге взаимодействия см. в разделе [маршалинг взаимодействия](../../../framework/interop/interop-marshaling.md).  
  
###### <a name="to-use-declare-and-marshalas-in-an-api-call"></a>Для использования в вызове API Declare и MarshalAs  
  
1.  Определите имя функции, необходимо вызвать ее аргументы, типы данных и возвращаемое значение.  
  
2.  Чтобы упростить доступ к `MarshalAs` , добавьте `Imports` в начало класса или модуля, как показано в следующем примере кода:  
  
     [!code-vb[VbVbalrInterop#13](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_4.vb)]  
  
3.  Добавьте прототип функции для импортированной функции в класс или модуль, использовании и применить `MarshalAs` атрибут параметров или возвращаемого значения. В следующем примере вызов API, который ожидает тип `void*` маршалируется как `AsAny`:  
  
     [!code-vb[VbVbalrInterop#14](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_5.vb)]  
  
## <a name="api-calls-using-dllimport"></a>Вызовы API, с помощью DllImport  
 `DllImport` Атрибут содержит второй способ вызова функций в библиотеках DLL без библиотеки типов. `DllImport` с помощью примерно соответствует `Declare` инструкции, но обеспечивает больший контроль над процессом вызова функций.  
  
 Можно использовать `DllImport` с большинства API Windows вызывает при условии, что вызов связан общий (иногда называется *статических*) метод. Нельзя использовать методы, которым требуется экземпляр класса. В отличие от `Declare` инструкций, `DllImport` вызовы нельзя использовать `MarshalAs` атрибута.  
  
#### <a name="to-call-a-windows-api-using-the-dllimport-attribute"></a>Для вызова API Windows, используя атрибут DllImport  
  
1.  Откройте новый проект приложения Windows, щелкнув **New** на **файл** меню и выбрав **проекта**. Откроется диалоговое окно **Новый проект** .  
  
2.  Выберите **приложение Windows** в списке шаблонов проектов Visual Basic. Откроется новый проект.  
  
3.  Добавьте кнопку с именем `Button2` форму запуска.  
  
4.  Дважды щелкните `Button2` открыть представление кода для формы.  
  
5.  Чтобы упростить доступ к `DllImport`, добавьте `Imports` в начало кода класса формы запуска:  
  
     [!code-vb[VbVbalrInterop#13](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_4.vb)]  
  
6.  Объявите пустую функцию выше `End Class` инструкции для формы и имя функции `MoveFile`.  
  
7.  Применить `Public` и `Shared` модификаторов для объявления функции, а также задавать параметры для `MoveFile` на основе аргументов использует функции Windows API:  
  
     [!code-vb[VbVbalrInterop#16](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_6.vb)]  
  
     Функция может иметь любое допустимое имя процедуры; `DllImport` атрибут указывает имя библиотеки DLL. Он также обрабатывает маршалинг взаимодействия для параметров и возвращаемых значений, поэтому можно выбрать типы данных Visual Studio, которые похожи на данные типы использует API.  
  
8.  Применить `DllImport` атрибута пустой функции. Первый параметр — имя и расположение библиотеки DLL, содержащей функцию, который вы вызываете. Необходимо указать путь к файлам, находящимся в системных каталогах Windows. Второй параметр — именованный аргумент, который задает имя функции в Windows API. В этом примере `DllImport` атрибут приводит вызовы `MoveFile` пересылать `MoveFileW` в KERNEL32. БИБЛИОТЕКИ DLL. `MoveFileW` Метод копирует файл из пути `src` путь `dst`.  
  
     [!code-vb[VbVbalrInterop#17](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_7.vb)]  
  
9. Добавьте код для `Button2_Click` обработчик событий для вызова функции:  
  
     [!code-vb[VbVbalrInterop#18](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_8.vb)]  
  
10. Создайте файл с именем Test.txt и поместите его в каталоге C:\Tmp на жестком диске. При необходимости создайте каталог Tmp.  
  
11. Нажмите клавишу F5 для запуска приложения. Появится главная форма.  
  
12. Нажмите кнопку **Button2**. Если файл можно переместить, отображается сообщение, «файл был перемещен успешно».  
  
## <a name="see-also"></a>См. также  
 <xref:System.Runtime.InteropServices.DllImportAttribute>  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md)  
 [Auto](../../../visual-basic/language-reference/modifiers/auto.md)  
 [Alias](../../../visual-basic/language-reference/statements/alias-clause.md)  
 [COM-взаимодействие](../../../visual-basic/programming-guide/com-interop/index.md)  
 [Создание прототипов в управляемом коде](../../../framework/interop/creating-prototypes-in-managed-code.md)  
 [Маршалинг делегата как метода обратного вызова](../../../framework/interop/marshaling-a-delegate-as-a-callback-method.md)
