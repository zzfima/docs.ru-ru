---
title: "Пошаговое руководство. Программирование приложений Office (C# и Visual Basic) | Документы Майкрософт"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- Office, programming in Visual Basic and C#
- Office programming [C#]
- Office programming [Visual Basic]
ms.assetid: 519cff31-f80b-4f0e-a56b-26358d0f8c51
caps.latest.revision: 46
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
ms.openlocfilehash: f93a5403660ca850d6650a1a6406395dfa2cc2e5
ms.lasthandoff: 03/13/2017

---
# <a name="walkthrough-office-programming-c-and-visual-basic"></a>Пошаговое руководство. Программирование приложений Office (C# и Visual Basic)
В Visual Studio в языках C# и Visual Basic появились новые функции, совершенствующие программирование для Microsoft Office. В каждый из языков были добавлены функции, которые уже имелись в другом языке.  
  
 К новым функциям C# относятся именованные и необязательные аргументы, возвращаемые значения с типом `dynamic`, возможность опускать ключевое слово `ref` и осуществлять доступ к индексированным свойствам при программировании в модели COM. Список новых функций Visual Basic включает автоматически реализуемые свойства, инструкции в лямбда-выражениях и инициализаторы коллекций.  
  
 Оба языка поддерживают внедрение сведений о типах, что позволяет развертывать сборки, взаимодействующие с компонентами COM, без предварительного развертывания на компьютере основных сборок взаимодействия (PIA). Дополнительные сведения см. в разделе [Пошаговое руководство. Внедрение данных о типах из управляемых сборок](http://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21).  
  
 В данном пошаговом руководстве эти новые возможности показаны в контексте программирования для Microsoft Office, но многие из них могут оказаться полезными и в других ситуациях. В этом пошаговом руководстве сначала будет необходимо создать книгу Excel с помощью надстройки Excel. После этого нужно будет создать документ Word, содержащий ссылку на эту книгу. Наконец, будет показано, как можно включать и отключать зависимость от сборок PIA.  
  
## <a name="prerequisites"></a>Предварительные требования  
 Для выполнения данного пошагового руководства на компьютере должны быть установлены Microsoft Office Excel 2013 (или версия 2007, или более поздняя) и Microsoft Office Word 2013 (или версия 2007, или более поздняя).  
  
 Если используется операционная система, более ранняя, чем [!INCLUDE[windowsver](../../../csharp/programming-guide/interop/includes/windowsver_md.md)], убедитесь, что установлена платформа [!INCLUDE[dnprdnlong](../../../csharp/programming-guide/events/includes/dnprdnlong_md.md)].  
  
[!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### <a name="to-set-up-an-excel-add-in-application"></a>Настройка надстройки Excel  
  
1.  Запустите Visual Studio.  
  
2.  В меню **Файл** выберите пункт **Создать**, а затем команду **Проект**.  
  
3.  В области **Установленные шаблоны** разверните узел **Visual Basic** или **Visual C#**, затем узел **Office** и щелкните **2013** (или **2010**, или **2007**).  
  
4.  В области **Шаблоны** щелкните **Надстройка Excel 2013** (или **Надстройка Excel 2010**, или **Надстройка Excel 2007**).  
  
5.  Убедитесь, что в верхней части области **Шаблоны** в поле **Требуемая версия .NET Framework** отображается **.NET Framework 4** или более поздняя версия.  
  
6.  Если нужно, в поле **Имя** введите имя проекта.  
  
7.  Нажмите кнопку **ОК**.  
  
8.  В **обозревателе решений** появится новый проект.  
  
### <a name="to-add-references"></a>Добавление ссылок  
  
1.  В **обозревателе решений** щелкните имя проекта правой кнопкой мыши и выберите пункт **Добавить ссылку**. Откроется диалоговое окно **Добавление ссылки**.  
  
2.  На вкладке **Сборки** в списке **Имя компонента** выберите **Microsoft.Office.Interop.Excel**, версия 15.0.0.0 (или версия 14.0.0.0 для Excel 2010, или версия 12.0.0.0 для Excel 2007), а затем, удерживая нажатой клавишу CTRL, выберите **Microsoft.Office.Interop.Word**, версия 15.0.0.0 (или версия 14.0.0.0 для Word 2010, или версия 12.0.0.0 для Word 2007).  Если сборки отсутствуют, может потребоваться проверить, что они установлены и отображаются (см. раздел [Практическое руководство. Установка основных сборок взаимодействия Microsoft Office](http://msdn.microsoft.com/library/92948fcc-76c6-4b08-ba63-cab59dd60eb1)).  
  
3.  Нажмите кнопку **ОК**.  
  
### <a name="to-add-necessary-imports-statements-or-using-directives"></a>Добавление необходимых операторов Imports или директив using  
  
1.  В **обозревателе решений** щелкните правой кнопкой мыши файл **ThisAddIn.vb** или **ThisAddIn.cs** и выберите в контекстном меню команду **Просмотреть код**.  
  
2.  В верхнюю часть файла с кодом добавьте следующие операторы `Imports` (Visual Basic) или директивы `using`, если это еще не сделано.  
  
     [!code-cs[csOfficeWalkthrough#1](../../../csharp/programming-guide/interop/codesnippet/CSharp/walkthrough-office-programming_1.cs)]
     [!code-vb[csOfficeWalkthrough#1](../../../csharp/programming-guide/interop/codesnippet/VisualBasic/walkthrough-office-programming_1.vb)]  
  
### <a name="to-create-a-list-of-bank-accounts"></a>Создание списка банковских счетов  
  
1.  В **обозревателе решений** щелкните правой кнопкой мыши имя проекта, выберите в контекстном меню команду **Добавить**, а затем щелкните пункт **Класс**. Назовите класс Account.vb, если используется Visual Basic, или Account.cs, если используется C#. Нажмите кнопку **Добавить**.  
  
2.  Замените определение класса `Account` следующим кодом. В определении класса используются *автоматически реализуемые свойства*. Это новая возможность Visual Basic в Visual Studio 2010. Дополнительные сведения см. в разделе [Автоматически реализуемые свойства](../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md).  
  
     [!code-cs[csOfficeWalkthrough#2](../../../csharp/programming-guide/interop/codesnippet/CSharp/walkthrough-office-programming_2.cs)]
     [!code-vb[csOfficeWalkthrough#2](../../../csharp/programming-guide/interop/codesnippet/VisualBasic/walkthrough-office-programming_2.vb)]  
  
3.  Чтобы создать список `bankAccounts`, содержащий два счета, добавьте в метод `ThisAddIn_Startup` в файле ThisAddIn.cs или ThisAddIn.vb следующий код. В объявлениях списков используются *инициализаторы коллекций*. Это новая возможность Visual Basic в Visual Studio 2010. Дополнительные сведения см. в разделе [Инициализаторы коллекций](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md).  
  
     [!code-cs[csOfficeWalkthrough#3](../../../csharp/programming-guide/interop/codesnippet/CSharp/walkthrough-office-programming_3.cs)]
     [!code-vb[csOfficeWalkthrough#3](../../../csharp/programming-guide/interop/codesnippet/VisualBasic/walkthrough-office-programming_3.vb)]  
  
### <a name="to-export-data-to-excel"></a>Экспорт данных в Excel  
  
1.  В том же самом файле добавьте в класс `ThisAddIn` следующий метод. Этот метод служит для настройки книги Excel и экспорта данных в нее.  
  
     [!code-cs[csOfficeWalkthrough#4](../../../csharp/programming-guide/interop/codesnippet/CSharp/walkthrough-office-programming_4.cs)]
     [!code-vb[csOfficeWalkthrough#4](../../../csharp/programming-guide/interop/codesnippet/VisualBasic/walkthrough-office-programming_4.vb)]  
  
     В этом методе используются две новые возможности C#. Оба эти возможности уже существуют в Visual Basic.  
  
    -   У метода [Add](http://go.microsoft.com/fwlink/?LinkId=210910) есть *необязательный параметр* для указания конкретного шаблона. Необязательные параметры, впервые появившиеся в [!INCLUDE[csharp_dev10_long](../../../csharp/programming-guide/classes-and-structs/includes/csharp_dev10_long_md.md)], позволяют опускать аргумент для таких параметров, если требуется использовать значение параметра по умолчанию. Поскольку в предыдущем примере никакой аргумент не передается, в методе `Add` используется шаблон по умолчанию и создается новая книга. В эквивалентном операторе в более ранних версиях C# необходимо было использовать аргумент-местозаполнитель `excelApp.Workbooks.Add(Type.Missing)`.  
  
         Дополнительные сведения см. в разделе [Именованные и необязательные аргументы](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md).  
  
    -   Свойства `Range` и `Offset` объекта [Range](http://go.microsoft.com/fwlink/?LinkId=210911) используют возможность *индексированных свойств*. Она позволяет использовать свойства типов COM с помощью стандартного синтаксиса C#. Кроме того, индексированные свойства позволяют использовать свойство `Value` объекта `Range`, устраняя необходимость в использовании свойства `Value2`. Свойство `Value` является индексированным, но индекс — необязательным. Совместная работа необязательных аргументов и индексированных свойств показана в следующем примере.  
  
         [!code-cs[csOfficeWalkthrough#5](../../../csharp/programming-guide/interop/codesnippet/CSharp/walkthrough-office-programming_5.cs)]  
  
         В более ранних версиях этого языка приходилось использовать особый синтаксис.  
  
         [!code-cs[csOfficeWalkthrough#6](../../../csharp/programming-guide/interop/codesnippet/CSharp/walkthrough-office-programming_6.cs)]  
  
         Разработчики не могут создавать собственные индексированные свойства. Эта возможность поддерживает только использование имеющихся индексированных свойств.  
  
         Дополнительные сведения см. в разделе [Практическое руководство. Использование индексированных свойств в программировании COM-взаимодействия](../../../csharp/programming-guide/interop/how-to-use-indexed-properties-in-com-interop-rogramming.md).  
  
2.  Добавьте в конец метода `DisplayInExcel` следующий код, чтобы ширина столбца изменялась в соответствии с содержимым.  
  
     [!code-cs[csOfficeWalkthrough#7](../../../csharp/programming-guide/interop/codesnippet/CSharp/walkthrough-office-programming_7.cs)]
     [!code-vb[csOfficeWalkthrough#7](../../../csharp/programming-guide/interop/codesnippet/VisualBasic/walkthrough-office-programming_7.vb)]  
  
     Эти дополнения демонстрируют еще одну новую возможность C# 2010: значения `Object`, возвращаемые главными приложениями COM, например приложениями Office, обрабатываются так, как если бы они имели тип [dynamic](../../../csharp/language-reference/keywords/dynamic.md). Это происходит автоматически, если параметр **Внедрить типы взаимодействия** имеет значение по умолчанию (`True`), или, что эквивалентно, если ссылка на сборку задается с помощью параметра компилятора [/link](../../../csharp/language-reference/compiler-options/link-compiler-option.md). Тип `dynamic` делает возможным позднее связывание, уже доступное в Visual Basic, и не допускает явного приведения, которое требовалось бы в Visual C# 2008 и более ранних версиях языка.  
  
     Например, `excelApp.Columns[1]` возвращает `Object`, а `AutoFit` является методом Excel [Range](http://go.microsoft.com/fwlink/?LinkId=210911). Без типа `dynamic` необходимо выполнять приведение объекта, возвращаемого `excelApp.Columns[1]`, к экземпляру `Range` перед вызовом метода `AutoFit`.  
  
     [!code-cs[csOfficeWalkthrough#8](../../../csharp/programming-guide/interop/codesnippet/CSharp/walkthrough-office-programming_8.cs)]  
  
     Дополнительные сведения о внедрении типов взаимодействия см. в подразделах "Поиск ссылки PIA" и "Восстановление зависимости PIA" далее в этом разделе. Дополнительные сведения о `dynamic` см. в разделе [dynamic](../../../csharp/language-reference/keywords/dynamic.md) или [Использование типа dynamic](../../../csharp/programming-guide/types/using-type-dynamic.md).  
  
### <a name="to-invoke-displayinexcel"></a>Вызов метода DisplayInExcel  
  
1.  Добавьте следующий код в конец метода `ThisAddIn_StartUp`. Вызов метода `DisplayInExcel` содержит два аргумента. Первый аргумент представляет собой имя списка счетов, которые требуется обработать. Второй аргумент — это состоящее из нескольких строк лямбда-выражение, которое определяет, каким образом следует обрабатывать данные. Значения `ID` и `balance` для каждого из счетов отображаются в соседних ячейках, а если баланс имеет отрицательное значение, строка отображается красным. Лямбда-выражения из нескольких строк являются новой возможностью Visual Basic 2010. Дополнительные сведения см. в разделе [Лямбда-выражения](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).  
  
     [!code-cs[csOfficeWalkthrough#9](../../../csharp/programming-guide/interop/codesnippet/CSharp/walkthrough-office-programming_9.cs)]
     [!code-vb[csOfficeWalkthrough#9](../../../csharp/programming-guide/interop/codesnippet/VisualBasic/walkthrough-office-programming_9.vb)]  
  
2.  Чтобы запустить программу, нажмите клавишу F5. Появится книга Excel, содержащая данные о счетах.  
  
### <a name="to-add-a-word-document"></a>Добавление документа Word  
  
1.  Добавьте в конец метода `ThisAddIn_StartUp` следующий код, чтобы создать документ Word, содержащий ссылку на книгу Excel.  
  
     [!code-cs[csOfficeWalkthrough#10](../../../csharp/programming-guide/interop/codesnippet/CSharp/walkthrough-office-programming_10.cs)]
     [!code-vb[csOfficeWalkthrough#10](../../../csharp/programming-guide/interop/codesnippet/VisualBasic/walkthrough-office-programming_10.vb)]  
  
     В этом коде демонстрируются некоторые новые функции C#: возможность опускать ключевое слово `ref` при программировании в модели COM, именованные аргументы и необязательные аргументы. Эти возможности уже существовали в Visual Basic. Метод [PasteSpecial](http://go.microsoft.com/fwlink/?LinkId=147099) имеет семь параметров, которые определены как необязательные ссылочные параметры. До появления Visual C# 2010 необходимо было определять объектные переменные, используемые в качестве аргументов для этих семи параметров, даже если с их помощью не требовалось передавать содержательные значения. Именованные и необязательные аргументы позволяют определять параметры, к которым требуется обращаться по имени, и передавать аргументы только для этих параметров. В этом примере аргументы передаются, чтобы показать, что необходимо создать ссылку на книгу в буфере (параметр `Link`) и что эта ссылка должна отображаться в документе Word в виде значка (параметр `DisplayAsIcon`). Кроме того, Visual C# 2010 позволяет опускать ключевое слово `ref` для таких аргументов. Сравните следующий фрагмент кода Visual C# 2008 с одной строкой в Visual C# 2010:  
  
     [!code-cs[csOfficeWalkthrough#11](../../../csharp/programming-guide/interop/codesnippet/CSharp/walkthrough-office-programming_11.cs)]  
  
### <a name="to-run-the-application"></a>Запуск приложения  
  
1.  Нажмите клавишу F5 для запуска приложения. Будет запущено приложение Excel, в котором будет открыта таблица, содержащая сведения о двух счетах из списка `bankAccounts`. Затем будет открыт документ Word, содержащий ссылку на таблицу Excel.  
  
### <a name="to-clean-up-the-completed-project"></a>Очистка готового проекта  
  
1.  В Visual Studio в меню **Построение** выберите пункт **Очистить решение**. В противном случае надстройка будет запускаться при каждом открытии Excel на компьютере разработчика.  
  
### <a name="to-find-the-pia-reference"></a>Поиск ссылки PIA  
  
1.  Запустите приложение снова, но не выбирайте пункт **Очистить решение**.  
  
2.  В меню **Пуск** выберите пункт **Все программы**. Затем последовательно выберите **Microsoft Visual Studio 2013**, **Visual Studio Tools** и **Командная строка Visual Studio (2013)**.  
  
3.  В окне командной строки Visual Studio 2013 введите команду `ildasm`, а затем нажмите клавишу ВВОД. Появится окно программы IL DASM.  
  
4.  В меню **Файл** в окне IL DASM выберите пункт **Открыть**. Дважды щелкните **Visual Studio 2013**, а затем дважды щелкните **Проекты**. Откройте папку проекта и найдите в папке bin/Debug файл *имя_проекта*.dll. Дважды щелкните файл *имя_проекта*.dll. В новом окне будут показаны атрибуты проекта, а также ссылки на другие модули и сборки. Обратите внимание, что в сборку включены пространства имен `Microsoft.Office.Interop.Excel` и `Microsoft.Office.Interop.Word`. По умолчанию в Visual Studio 2013 компилятор импортирует в сборку необходимые типы из сборки PIA, на которую указывает ссылка.  
  
     Дополнительные сведения см. в разделе [Практическое руководство. Просмотр содержимого сборок](http://msdn.microsoft.com/library/fb7baaab-4c0d-47ad-8fd3-4591cf834709).  
  
5.  Дважды щелкните значок **МАНИФЕСТ**. Откроется окно со списком сборок, содержащих элементы, на которые имеются ссылки в проекте. Сборки `Microsoft.Office.Interop.Excel`и `Microsoft.Office.Interop.Word` не будут указаны в этом списке. Поскольку необходимые для проекта типы были импортированы в сборку проекта, ссылки на сборки PIA не требуется. Это упрощает развертывание. Сборки PIA не обязательно должны присутствовать на компьютере пользователя, а поскольку приложение не требует развертывания конкретной версии сборки PIA, можно разрабатывать приложения, которые работают с различными версиями Office, если в этих версиях имеются все необходимые интерфейсы API.  
  
     Поскольку развертывать сборки PIA больше не требуется, можно создавать приложения для применения в сложных сценариях, чтобы эти приложения работали с несколькими версиями Office, включая и более ранние версии. Тем не менее это возможно только в том случае, если в коде не используются интерфейсы API, которые недоступны в используемой версии Office. Разработчик не всегда знает, был ли доступен тот или иной интерфейс API в более ранней версии, поэтому работать с более ранними версиями Office не рекомендуется.  
  
    > [!NOTE]
    >  До Office 2003 сборки PIA не публиковались. Поэтому единственными способом создания сборки взаимодействия в Office 2002 или более ранних версиях является импорт ссылки COM.  
  
6.  Закройте окно манифеста и окно сборки.  
  
### <a name="to-restore-the-pia-dependency"></a>Восстановление зависимости PIA  
  
1.  В **обозревателе решений** нажмите кнопку **Показать все файлы**. Разверните папку **Ссылки** и выберите **Microsoft.Office.Interop.Excel**. Нажмите клавишу F4, чтобы открыть окно **Свойства**.  
  
2.  В окне **Свойства** измените значение свойства **Внедрить типы взаимодействия** с **True** на **False**.  
  
3.  Повторите шаги 1 и 2 этой процедуры для сборки `Microsoft.Office.Interop.Word`.  
  
4.  В C# раскомментируйте два вызова метода `Autofit` в конце метода `DisplayInExcel`.  
  
5.  Нажмите клавишу F5, чтобы проверить, что проект по-прежнему выполняется правильно.  
  
6.  Повторите шаги 1–3 из предыдущей процедуры, чтобы открыть окно сборки. Обратите внимание, что сборки `Microsoft.Office.Interop.Word` и `Microsoft.Office.Interop.Excel` больше не входят в список внедренных сборок.  
  
7.  Дважды щелкните значок **МАНИФЕСТ** и просмотрите список сборок, на которые имеются ссылки. В списке будут указаны сборки `Microsoft.Office.Interop.Word` и `Microsoft.Office.Interop.Excel`. Поскольку приложение содержит ссылки на сборки PIA Excel и Word, а свойство **Внедрить типы взаимодействия** имеет значение **False**, на компьютере пользователя должны храниться обе сборки.  
  
8.  В Visual Studio в меню **Построение** выберите пункт **Очистить решение**, чтобы очистить завершенный проект.  
  
## <a name="see-also"></a>См. также  
 [Автоматически реализуемые свойства](../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md)   
 [Автоматически реализуемые свойства](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md)   
 [Инициализаторы коллекций](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)   
 [Инициализаторы объектов и коллекций](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)   
 [Необязательные параметры](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)   
 [Передача аргументов по позиции и по имени](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md)   
 [Именованные и необязательные аргументы](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md)   
 [Раннее и позднее связывание](../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)   
 [dynamic](../../../csharp/language-reference/keywords/dynamic.md)   
 [Использование типа dynamic](../../../csharp/programming-guide/types/using-type-dynamic.md)   
 [Лямбда-выражения](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)   
 [Лямбда-выражения](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)   
 [Практическое руководство. Использование индексированных свойств в программировании COM-взаимодействия](../../../csharp/programming-guide/interop/how-to-use-indexed-properties-in-com-interop-rogramming.md)   
 [Пошаговое руководство. Внедрение данных о типе из сборок для приложений Microsoft Office](http://msdn.microsoft.com/library/85b55e05-bc5e-4665-b6ae-e1ada9299fd3)   
 [Пошаговое руководство. Внедрение данных о типах из управляемых сборок](http://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21)   
 [Walkthrough: Creating Your First VSTO Add-in for Excel](http://msdn.microsoft.com/library/a855e2be-3ecf-4112-a7f5-ec0f7fad3b5f)  (Пошаговое руководство. Создание первой надстройки VSTO для Excel)  
 [COM-взаимодействие](../../../visual-basic/programming-guide/com-interop/index.md)   
 [Взаимодействие](../../../csharp/programming-guide/interop/index.md)
