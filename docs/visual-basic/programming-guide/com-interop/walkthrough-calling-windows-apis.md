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
ms.openlocfilehash: 59c316ccb3a35a650ac11b96717a3ad729e777a3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54657978"
---
# <a name="walkthrough-calling-windows-apis-visual-basic"></a>Пошаговое руководство. Вызов API Windows (Visual Basic)
API-интерфейсы Windows, библиотеки динамической компоновки (DLL), которые являются частью операционной системы Windows. Они используются для выполнения задач при очень трудно написать собственную процедуру. Например, Windows предоставляет функцию с именем `FlashWindowEx` , позволяющий изменять строку заголовка приложения от светлые и темные оттенки.  
  
 Преимущество использования интерфейсов API Windows в коде является то, что это может сократить время разработки, так как они содержат множество полезных функций, которые уже записаны и ждут. Недостатком является то, что API-интерфейсы Windows может быть трудно работать с и не реагирует, когда что-то пошло.  
  
 API-интерфейсы Windows представляют собой специальную категорию взаимодействия. API-интерфейсы Windows следует использовать управляемый код, не имеют встроенных библиотек и использовать типы данных, которые отличаются от тех, которые используются в Visual Studio. Из-за этих различий и так как API-интерфейсы Windows не являются объектами COM, взаимодействие с API-интерфейсов Windows и [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] выполняется с помощью платформы неуправляемого кода, или PInvoke. Неуправляемого кода — это служба, позволяющая управляемому коду вызывать неуправляемые функции, реализованные в библиотеках DLL. Дополнительные сведения см. в разделе [использование неуправляемых функций DLL](../../../framework/interop/consuming-unmanaged-dll-functions.md). Можно использовать PInvoke в Visual Basic с помощью `Declare` инструкции или применение `DllImport` атрибут к пустой процедуре.  
  
 Вызовы Windows API были важной частью программирования в прошлом Visual Basic, но редко необходимы в Visual Basic .NET. По возможности следует использовать управляемый код из [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] для выполнения задач, а не вызовы Windows API. Это пошаговое руководство содержит сведения для таких случаев, в которых использование API-интерфейсы Windows не требуется.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="api-calls-using-declare"></a>Объявить с помощью вызовов API  
 Является наиболее распространенным способом для вызова Windows API с помощью `Declare` инструкции.  
  
#### <a name="to-declare-a-dll-procedure"></a>Объявление процедуры DLL  
  
1.  Определить имя функции, которые вы хотите вызвать, ее аргументы, типы аргументов и возвращают значение, а также имя и расположение библиотеки DLL, которая его содержит.  
  
    > [!NOTE]
    >  Полные сведения об API-интерфейсы Windows см. в документации Win32 SDK, в Windows API пакета SDK для платформы. Дополнительные сведения о константах, использующих API-интерфейсы Windows проверьте файлы заголовков, такие как Windows.h, входящего в пакет SDK платформы.  
  
2.  Откройте новый проект приложения Windows, щелкнув **New** на **файл** меню, а затем щелкнув **проекта**. Откроется диалоговое окно **Новый проект** .  
  
3.  Выберите **приложения Windows** в списке шаблонов проектов Visual Basic. Откроется новый проект.  
  
4.  Добавьте следующий `Declare` работать либо на класс или модуль, в котором вы хотите использовать библиотеку DLL:  
  
     [!code-vb[VbVbalrInterop#9](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_1.vb)]  
  
### <a name="parts-of-the-declare-statement"></a>Части оператор Declare  
 `Declare` Инструкция включает в себя следующие элементы.  
  
#### <a name="auto-modifier"></a>Модификатор Auto  
 `Auto` Модификатор указывает среде выполнения для преобразования строки, на основе имени метода в соответствии с общих правил языка среды выполнения (или псевдоним, если указано).  
  
#### <a name="lib-and-alias-keywords"></a>Ключевые слова lib и псевдоним  
 Следующее имя `Function` ключевое слово — это имя, программа использует для доступа к импортируемой функции. Он может совпадать с действительное имя вызываемой функции, или можно использовать любой допустимым именем процедуры и затем использовали `Alias` ключевое слово, чтобы указать действительное имя вызываемой функции.  
  
 Укажите `Lib` ключевое слово, за которым следует имя и расположение библиотеки DLL, содержащей функцию, вы вызываете. Необходимо указать путь для файлов в файловой системы Windows.  
  
 Используйте `Alias` ключевое слово, имя функции при вызове не является допустимым именем процедуры Visual Basic или конфликтует с именем других элементов в приложении. `Alias` Указывает правильное имя вызываемой функции.  
  
#### <a name="argument-and-data-type-declarations"></a>Аргумент и объявлениям типов данных  
 Объявите аргументы и их типы данных. Эта часть может оказаться сложной задачей, поскольку типы данных, которые использует Windows не соответствуют типам данных Visual Studio. Visual Basic выполняет большую часть работы автоматически путем преобразования аргументов в совместимые типы данных, этот процесс называется *маршалинг*. Можно явно управлять маршалингом аргументов с помощью <xref:System.Runtime.InteropServices.MarshalAsAttribute> атрибутом, определенным в <xref:System.Runtime.InteropServices> пространства имен.  
  
> [!NOTE]
>  Предыдущие версии Visual Basic позволяет объявлять параметры `As Any`, то есть, данные любого типа может использоваться. Visual Basic необходимо использовать определенный тип данных для всех `Declare` инструкций.  
  
#### <a name="windows-api-constants"></a>Константы Windows API  
 Некоторые аргументы являются сочетаниями констант. Например `MessageBox` API, приведенных в этом руководстве принимает целочисленный аргумент вызывается `Typ` , определяет, как отображается окно сообщения. Числовое значение из этих констант можно определить с помощью проверки `#define` инструкций в файле WinUser.h. Числовые значения обычно отображаются в шестнадцатеричном формате, поэтому может потребоваться добавить их и преобразовать в десятичное с помощью калькулятора. К примеру, если нужно объединить константы для стиля восклицательный знак `MB_ICONEXCLAMATION` 0x00000030 и Да/Нет стиля `MB_YESNO` 0x00000004, можно добавить номера и получить результат 0x00000034, или 52 десятичное. Несмотря на то, что можно использовать непосредственно десятичное число, лучше объявить эти значения в приложении как константы, а также объединять их с помощью `Or` оператор.  
  
###### <a name="to-declare-constants-for-windows-api-calls"></a>Для объявления констант для вызовов Windows API  
  
1.  См. в документации для вызова функции Windows. Определите имя константы, используемые в нем и имя файла .h, который содержит числовые значения для этих констант.  
  
2.  Используйте текстовый редактор, например Блокнот, чтобы просмотреть содержимое файла заголовка (.h) и найдите значения, связанные с константами, которую вы используете. Например `MessageBox` API использует константа `MB_ICONQUESTION` Показать знак вопроса в окне сообщения. Определение `MB_ICONQUESTION` в WinUser.h и выглядит следующим образом:  
  
     `#define MB_ICONQUESTION             0x00000020L`  
  
3.  Добавьте соответствующие `Const` инструкции, чтобы класс или модуль, чтобы сделать эти константы доступными для приложения. Пример:  
  
     [!code-vb[VbVbalrInterop#11](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_2.vb)]  
  
###### <a name="to-call-the-dll-procedure"></a>Вызов процедуры DLL  
  
1.  Добавьте кнопку с именем `Button1` запуска форму для проекта и дважды щелкните его, чтобы просмотреть ее код. Обработчик событий для кнопки отображается.  
  
2.  Добавьте код для `Click` обработчик событий для кнопки, вы добавили, чтобы вызвать процедуру и предоставьте соответствующие аргументы:  
  
     [!code-vb[VbVbalrInterop#12](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_3.vb)]  
  
3.  Запустите проект, нажав клавишу F5. Окно сообщения отображается с обоими **Да** и **нет** кнопками. Нажмите одну из них.  
  
#### <a name="data-marshaling"></a>Маршалинг данных  
 Visual Basic автоматически преобразует типы данных параметров и возвращаемых значений для вызовов Windows API, но можно использовать `MarshalAs` атрибута в явном виде неуправляемые типы данных, которые ожидает API. Дополнительные сведения о маршалинге взаимодействия см. в разделе [маршалинг взаимодействия](../../../framework/interop/interop-marshaling.md).  
  
###### <a name="to-use-declare-and-marshalas-in-an-api-call"></a>Использовать Declare и MarshalAs в вызов API  
  
1.  Определить имя функции, необходимо вызвать ее аргументы, типы данных и возвращают значение.  
  
2.  Для упрощения доступа к `MarshalAs` атрибута, добавьте `Imports` в начало кода для класса или модуля, как показано в следующем примере:  
  
     [!code-vb[VbVbalrInterop#13](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_4.vb)]  
  
3.  Добавьте прототип функции для импортированной функции в класс или модуль, вы используете и применить `MarshalAs` атрибут параметров или возвращаемого значения. В следующем примере вызов API, который ожидает, что тип `void*` маршалируется как `AsAny`:  
  
     [!code-vb[VbVbalrInterop#14](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_5.vb)]  
  
## <a name="api-calls-using-dllimport"></a>Вызовы API, с помощью DllImport  
 `DllImport` Атрибут предоставляет второй способ вызова функций в библиотеках DLL без библиотеки типов. `DllImport` с помощью приблизительно соответствует `Declare` инструкции, но обеспечивает больший контроль над процессом вызова функций.  
  
 Можно использовать `DllImport` с большинства API Windows вызывает до тех пор, пока вызов связан общий (иногда называется *статический*) метод. Нельзя использовать методы, которым требуется экземпляр класса. В отличие от `Declare` инструкций, `DllImport` нельзя использовать вызовы `MarshalAs` атрибута.  
  
#### <a name="to-call-a-windows-api-using-the-dllimport-attribute"></a>Для вызова API Windows, используя атрибут DllImport  
  
1.  Откройте новый проект приложения Windows, щелкнув **New** на **файл** меню, а затем щелкнув **проекта**. Откроется диалоговое окно **Новый проект** .  
  
2.  Выберите **приложения Windows** в списке шаблонов проектов Visual Basic. Откроется новый проект.  
  
3.  Добавьте кнопку с именем `Button2` форму запуска.  
  
4.  Дважды щелкните `Button2` чтобы открыть представление кода для формы.  
  
5.  Для упрощения доступа к `DllImport`, добавьте `Imports` в начало кода для класса формы запуска:  
  
     [!code-vb[VbVbalrInterop#13](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_4.vb)]  
  
6.  Объявите пустую функцию выше `End Class` инструкции для формы и имя функции `MoveFile`.  
  
7.  Применить `Public` и `Shared` модификаторы объявления функции, а также задавать параметры для `MoveFile` на основе аргументов в функции Windows API используется:  
  
     [!code-vb[VbVbalrInterop#16](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_6.vb)]  
  
     Функция может иметь любое допустимое имя процедуры; `DllImport` атрибут указывает имя библиотеки DLL. Он также обрабатывает маршалинг взаимодействия для параметров и возвращаемых значений, поэтому вы можете выбрать типы данных Visual Studio, которые похожи на данные типах, которые использует API.  
  
8.  Применить `DllImport` атрибут пустой функции. Первый параметр — это имя и расположение библиотеки DLL, содержащей функцию, которую вы вызываете. Необходимо указать путь для файлов в файловой системы Windows. Второй параметр — именованный аргумент, который задает имя функции в Windows API. В этом примере `DllImport` атрибут приводит вызовы `MoveFile` должно перенаправляться в `MoveFileW` в KERNEL32. БИБЛИОТЕКА DLL. `MoveFileW` Метод копирует файл из пути `src` путь `dst`.  
  
     [!code-vb[VbVbalrInterop#17](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_7.vb)]  
  
9. Добавьте код для `Button2_Click` обработчик событий для вызова функции:  
  
     [!code-vb[VbVbalrInterop#18](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_8.vb)]  
  
10. Создайте файл с именем Test.txt и поместите его в каталог C:\Tmp на жестком диске. При необходимости создайте каталог Tmp.  
  
11. Нажмите клавишу F5 для запуска приложения. Появится главная форма.  
  
12. Нажмите кнопку **Button2**. Если файл можно переместить, отображается сообщение, «файл был перемещен успешно».  
  
## <a name="see-also"></a>См. также
- <xref:System.Runtime.InteropServices.DllImportAttribute>
- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md)
- [Auto](../../../visual-basic/language-reference/modifiers/auto.md)
- [Alias](../../../visual-basic/language-reference/statements/alias-clause.md)
- [COM-взаимодействие](../../../visual-basic/programming-guide/com-interop/index.md)
- [Создание прототипов в управляемом коде](../../../framework/interop/creating-prototypes-in-managed-code.md)
- [Маршалинг делегата как метода обратного вызова](../../../framework/interop/marshaling-a-delegate-as-a-callback-method.md)
