---
title: "Пошаговое руководство. Вызов API Windows (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "вызовы API, пошаговые руководства [Visual Basic]"
  - "Declare - оператор, объявление функций DLL"
  - "DllImport - атрибут, вызов Windows API"
  - "библиотеки DLL, вызов"
  - "вызов неуправляемого кода, пошаговые руководства"
  - "пошаговые руководства [Visual Basic], вызовы API"
  - "API Windows, вызов"
  - "API Windows, пошаговые руководства"
ms.assetid: 9280ca96-7a93-47a3-8d01-6d01be0657cb
caps.latest.revision: 20
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 20
---
# Пошаговое руководство. Вызов API Windows (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Интерфейсы Windows API являются динамическими библиотеками \(DLL\), частью операционной системы Windows.   Они используются для решения задач в том случае, когда сложно написать собственную соответствующую процедуру.  Например, в Windows есть функция под названием `FlashWindowEx`, позволяющая изменять строку заголовка приложения от светлого оттенка к темному.  
  
 Преимущество применения интерфейсов Windows API в коде состоит в том, что это может сократить время разработки программы, поскольку программиста ждут десятки готовых полезных и удобных функций.  Недостатки использования Windows API — с ними может оказаться непросто работать, и они не терпят ошибок.  
  
 Интерфейсы Windows API представляют собой специальную категорию взаимодействия.  Интерфейсы Windows API не используют управляемый код, не имеют встроенных библиотек и пользуются типами данных, отличными от применяемых Visual Studio.  Из\-за перечисленных различий, а также потому, что интерфейсы Windows API не являются объектами COM, взаимодействие между интерфейсами Windows API и [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] выполняется с привлечением платформенного вызова или PInvoke.  Платформенным вызовом называется служба, позволяющая управляемому коду вызывать реализованные в DLL неуправляемые функции.  Дополнительные сведения см. в разделе [Consuming Unmanaged DLL Functions](../Topic/Consuming%20Unmanaged%20DLL%20Functions.md).  Можно использовать PInvoke в [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)], используя либо инструкцию `Declare`, либо применения атрибута `DllImport` к пустой процедуре.  
  
 Вызовы Windows API были важной частью программирования Microsoft [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] в прошлом, но редко необходимы с [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong-md.md)].  При возможности для выполнения задач следует пользоваться управляемым кодом [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)], а не вызовом Windows API.  В этом пошаговом руководстве демонстрируются ситуации, когда необходимо использование интерфейсов Windows API.  
  
 [!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note-settings-general-md.md)]  
  
## Вызов API с помощью оператора Declare  
 Самый распространенный способ вызова интерфейса Windows API — посредством оператора `Declare`.  
  
#### Объявление процедуры DLL  
  
1.  Определите имя функции, которую необходимо вызвать, ее аргументы, типы аргументов, возвращаемое значение, а также имя и расположение содержащей ее библиотеки DLL.  
  
    > [!NOTE]
    >  Для получения полных сведений об интерфейсе Windows API обратитесь к документации Win32 SDK в Platformе SDK Windows API.  Для получения сведений об используемых интерфейсом Windows API константах см. включенные в Platform SDK файлы заголовков, например Windows.h.  
  
2.  Создайте новый проект "Приложение Windows", щелкнув пункт **Создать** в меню **Файл**, а затем выбрав **Проект**.  Откроется диалоговое окно **Новый проект**.  
  
3.  Выберите **Приложение Windows** из списка шаблонов проектов [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)].  Появится новый проект.  
  
4.  Добавьте следующую функцию `Declare` либо в класс, либо в модуль, в котором требуется использование DLL:  
  
     [!code-vb[VbVbalrInterop#9](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_1.vb)]  
  
### Составляющие оператора Declare  
 Оператор `Declare` включает следующие элементы:  
  
#### Модификатор Auto  
 Модификатор `Auto` инструктирует среду выполнения о необходимости преобразования строки на основе имени метода в соответствии с правилами общеязыковой среды выполнения \(или именами\-псевдонимами, если они указаны\).  
  
#### Ключевые слова Lib и Alias  
 Имя, которое следует за ключевым словом `Function` — это имя, которое программа использует для доступа к импортируемой функции.  Оно может быть идентичным настоящему имени вызываемой функции. Другой способ — воспользоваться любым допустимым именем процедуры, а затем задействовать ключевое слово `Alias`, чтобы указать настоящее имя вызываемой функции.  
  
 Примените ключевое слово `Lib`, за которым следует имя и расположение файла DLL, в котором хранится вызываемая функция.  Для файлов, расположенных в системных каталогах Windows, указывать путь не требуется.  
  
 Ключевое слово `Alias` следует использовать, если имя вызываемой функции не является допустимым именем процедуры [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] или конфликтует с именем других элементов в приложении.  Ключевое слово `Alias` указывает правильное имя вызываемой функции.  
  
#### Объявление аргументов и типов данных  
 Объявите аргументы и их типы данных.  Эта задача может быть достаточно сложной, поскольку типы данных, используемые в Windows, не соответствуют типам данных Visual Studio.  [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] выполняет большой объем работы за разработчика, преобразуя аргументы в совместимые типы данных. Этот процесс называется *маршалингом*.  Можно явным образом управлять маршалингом аргументов с помощью атрибута <xref:System.Runtime.InteropServices.MarshalAsAttribute>, определенного в пространстве имен <xref:System.Runtime.InteropServices>.  
  
> [!NOTE]
>  Предыдущие версии [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] позволяли объявлять параметры `As Any`, означающие, что могут использоваться данные любого типа.  В [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] необходимо использовать определенный тип данных для всех инструкций `Declare`.  
  
#### Константы интерфейса Windows API  
 Некоторые аргументы являются сочетаниями констант.  Например, рассматриваемый в этом пошаговом руководстве интерфейс API `MessageBox` принимает целочисленный аргумент под названием `Typ`, который определяет вид окна сообщения.  Определите имя числовое значение этих констант, изучив инструкции `#define` в файле WinUser.h.  Числовые значения, как правило, приведены в шестнадцатеричной системе счисления, поэтому, возможно, потребуется воспользоваться калькулятором для их сложения и преобразования в десятичную систему счисления.   Например, если необходимо сложить константы стиля восклицания `MB_ICONEXCLAMATION` 0x00000030 и стиля "Да\/Нет" `MB_YESNO` 0x00000004, можно сложить эти числа и получить результат 0x00000034, или 52 в десятичном счислении.  Несмотря на то, что можно использовать непосредственно десятичное число, корректнее объявить эти значения в приложении как константы и сочетать их при помощи оператора `Or`.  
  
###### Объявление констант для вызовов интерфейса Windows API  
  
1.  Обратитесь к документации для вызываемой функции Windows.  Определите имя константы, которую она использует, и имя H\-файла \(с расширением .h\), который содержит числовые значения для этих констант.  
  
2.  Чтобы просмотреть содержимое файла заголовка \(H\-файла\) и найти соответствующие применяемым константам значения, используйте текстовый редактор, например "Блокнот".  Например API\-интерфейс `MessageBox` использует константу `MB_ICONQUESTION`, чтобы показать знак вопроса в окне сообщения.  Определением для `MB_ICONQUESTION` является WinUser.h, и выглядит оно следующим образом:  
  
     `#define MB_ICONQUESTION             0x00000020L`  
  
3.  Добавьте соответствующие инструкции `Const` в ваш класс или модуль, чтобы сделать эти константы доступными для приложения.  Примеры.  
  
     [!code-vb[VbVbalrInterop#11](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_2.vb)]  
  
###### Вызов процедуры DLL  
  
1.  Добавьте в форму запуска проекта кнопку под названием `Button1`, а затем выполните на ней двойной щелчок мышью, чтобы просмотреть код.  Появится обработчик событий для данной кнопки.  
  
2.  Вставьте в обработчик событий `Click` новой кнопки следующий код, чтобы вызвать процедуру, и предоставьте соответствующие аргументы:  
  
     [!code-vb[VbVbalrInterop#12](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_3.vb)]  
  
3.  Запустите проект, нажав клавишу F5.  Появится окно сообщений с кнопками **Да** и **Нет**.  Нажмите одну из них.  
  
#### Маршалинг данных  
 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]автоматически преобразует типы данных параметров и возвращаемых значений вызовов интерфейса Windows API, но можно также применить атрибут `MarshalAs`, чтобы явным образом определить ожидаемые интерфейсом API неуправляемые типы данных.  Дополнительные сведения о маршалинге взаимодействия содержатся в разделе [Interop Marshaling](../Topic/Interop%20Marshaling.md).  
  
###### Использование при вызове интерфейса API оператора Declare и атрибута MarshalAs  
  
1.  Выясните имя вызываемой функции, ее аргументы, типы данных и возвращаемое значение.  
  
2.  Чтобы упростить доступ к атрибуту `MarshalAs`, в начале кода класса или модуля вставьте оператор `Imports`, как показано в следующем примере:  
  
     [!code-vb[VbVbalrInterop#13](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_4.vb)]  
  
3.  Добавьте прототип функции для импортированной функции в класс или модуль, который вы используете, и примените атрибут `MarshalAs` к параметрам или возвращаемому значению.  В следующем примере демонстрируется вызов API, предполагающий маршалинг типа `void*` как `AsAny`:  
  
     [!code-vb[VbVbalrInterop#14](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_5.vb)]  
  
## Вызов интерфейса API с помощью атрибута DllImport  
 Атрибут `DllImport` реализует второй способ вызова функций в DLL без библиотек типов.  `DllImport` в общих чертах похож на инструкцию `Declare`, но обеспечивает больший контроль над процессом вызова функций.  
  
 Атрибут `DllImport` можно применять с большинством вызовов интерфейса Windows API, при условии, что вызов связан с общим \(иначе называемым *статическим*\) методом.  Нельзя использовать методы, которым требуется экземпляр класса.  В отличие от инструкций `Declare`, вызовы`DllImport` не могут использовать атрибут `MarshalAs`.  
  
#### Вызов интерфейса Windows API с помощью атрибута DllImport  
  
1.  Создайте новый проект "Приложение Windows", щелкнув пункт **Создать** в меню **Файл**, а затем выбрав **Проект**.  Откроется диалоговое окно **Новый проект**.  
  
2.  Выберите **Приложение Windows** из списка шаблонов проектов [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)].  Появится новый проект.  
  
3.  Добавьте кнопку с именем `Button2` в начальную форму.  
  
4.  Дважды щелкните кнопку `Button2`, чтобы просмотреть код формы.  
  
5.  Чтобы упростить доступ к атрибуту `DllImport`, в начале кода класса начальной формы вставьте оператор `Imports`:  
  
     [!code-vb[VbVbalrInterop#13](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_4.vb)]  
  
6.  Перед оператором формы `End Class` объявите пустую функцию и озаглавьте ее `MoveFile`.  
  
7.  Примените к объявлению функции модификаторы `Public` и `Shared` и установите для `MoveFile` параметры на основе аргументов, используемых функцией Windows API:  
  
     [!code-vb[VbVbalrInterop#16](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_6.vb)]  
  
     Функция может иметь любое допустимое имя процедуры; атрибут `DllImport` задает это имя в библиотеке DLL.  Кроме того, он управляет маршалингом взаимодействия для параметров и возвращаемых значений, поэтому есть возможность выбрать типы данных Visual Studio, аналогичные типам данных, используемым в API.  
  
8.  Примените к пустой функции атрибут `DllImport`.  Первый параметр — имя и расположение библиотеки DLL, в котором хранится вызываемая функция.  Для файлов, расположенных в системных каталогах Windows, указывать путь не требуется.  Второй параметр — именованный аргумент, который задает имя функции в Windows API.  В этом примере атрибут `DllImport` принудительно перенаправляет вызовы `MoveFile` к `MoveFileW` в Kernel32.dll.  Метод `MoveFileW` копирует файл из пути `src` в путь `dst`.  
  
     [!code-vb[VbVbalrInterop#17](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_7.vb)]  
  
9. Для вызова функции добавьте в обработчик событий `Button2_Click` следующий код:  
  
     [!code-vb[VbVbalrInterop#18](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_8.vb)]  
  
10. Создайте файл с именем Test.txt и поместите его на жесткий диск в каталог C:\\Tmp.  При необходимости создайте каталог Tmp.  
  
11. Нажмите клавишу F5 для запуска приложения.  Появится главная форма.  
  
12. Нажмите кнопку **Button2**.  Если файл можно перемещать, появится сообщение "The file was moved successfully" \("Файл успешно перемещен"\).  
  
## См. также  
 <xref:System.Runtime.InteropServices.DllImportAttribute>   
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md)   
 [Auto](../../../visual-basic/language-reference/modifiers/auto.md)   
 [Alias](../../../visual-basic/language-reference/statements/alias-clause.md)   
 [COM\-взаимодействие](../../../visual-basic/programming-guide/com-interop/index.md)   
 [Creating Prototypes in Managed Code](../Topic/Creating%20Prototypes%20in%20Managed%20Code.md)   
 [Marshaling a Delegate as a Callback Method](../Topic/Marshaling%20a%20Delegate%20as%20a%20Callback%20Method.md)