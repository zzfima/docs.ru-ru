---
title: Создание пользовательских прослушивателей журнала (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- custom log listeners
- My.Application.Log object, custom log listeners
ms.assetid: 0e019115-4b25-4820-afb1-af8c6e391698
ms.openlocfilehash: 298bfa2987397591492480d953949d20168785bf
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2019
ms.locfileid: "72581687"
---
# <a name="walkthrough-creating-custom-log-listeners-visual-basic"></a>Пошаговое руководство. Создание пользовательских прослушивателей журнала (Visual Basic)

В этом пошаговом руководстве демонстрируется создание пользовательского прослушивателя журнала и его настройка на прослушивание выходных данных объекта `My.Application.Log`.

## <a name="getting-started"></a>Начало работы

Прослушиватели журналов должны наследовать от класса <xref:System.Diagnostics.TraceListener>.

#### <a name="to-create-the-listener"></a>Создание прослушивателя

- В приложении создайте класс с именем `SimpleListener`, который наследует от класса <xref:System.Diagnostics.TraceListener>.

     [!code-vb[VbVbalrMyApplicationLog#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#16)]

     Методы <xref:System.Diagnostics.TraceListener.Write%2A> и <xref:System.Diagnostics.TraceListener.WriteLine%2A>, которые нужны для базового класса, используют `MsgBox` для отображения входных данных.

     К методам <xref:System.Diagnostics.TraceListener.Write%2A> и <xref:System.Diagnostics.TraceListener.WriteLine%2A> применяется атрибут <xref:System.Security.Permissions.HostProtectionAttribute>, чтобы их атрибуты соответствовали методы базового класса. Атрибут <xref:System.Security.Permissions.HostProtectionAttribute> позволяет узлу, на котором выполняется код, проверять наличие в коде синхронизации защиты узла.

    > [!NOTE]
    > Атрибут <xref:System.Security.Permissions.HostProtectionAttribute> действует только для неуправляемых приложений, на которых размещена среда CLR и реализована защита узлов, например для SQL Server.

Чтобы объект `My.Application.Log` использовал прослушиватель журнала, следует присвоить строгое имя сборке, содержащей прослушиватель журнала.

В следующей процедуре показано несколько простых шагов по созданию сборки прослушивателя журнала со строгим именем. Дополнительные сведения см. в разделе [Создание и использование сборок со строгими именами](../../../../standard/assembly/create-use-strong-named.md).

#### <a name="to-strongly-name-the-log-listener-assembly"></a>Задание строгого имени сборке прослушивателя журнала

1. Выберите проект в **Обозревателе решений**. В меню **Проект** выберите пункт **Свойства**.

2. Откройте вкладку **Подписывание**.

3. Выберите поле **Подписать сборку**.

4. В раскрывающемся списке **Выберите файл ключа строгого имени** щелкните **\<Новый...>** .

     Откроется диалоговое окно **Создание ключа строгого имени**.

5. Укажите имя для файла ключа в поле **Имя файла ключа**.

6. Введите пароль в поля **Введите пароль** и **Подтверждение пароля**.

7. Нажмите кнопку **ОК**.

8. Перестройте приложение.

## <a name="adding-the-listener"></a>Добавление прослушивателя

Теперь, когда сборка имеет строгое имя, необходимо определить строгое имя прослушивателя, чтобы объект `My.Application.Log` использовал прослушиватель журнала.

Тип со строгим именем имеет следующий формат:

\<имя типа>, \<имя сборки>, \<номер версии>, \<язык>, \<строгое имя>

#### <a name="to-determine-the-strong-name-of-the-listener"></a>Определение строгого имени прослушивателя

- В следующем коде показано, как определить строгое имя типа для `SimpleListener`.

     [!code-vb[VbVbalrMyApplicationLog#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#17)]

     Строгое имя типа зависит от проекта.

Можно добавить прослушиватель со строгим именем в коллекцию прослушивателей журнала `My.Application.Log`.

#### <a name="to-add-the-listener-to-myapplicationlog"></a>Добавление прослушивателя в My.Application.Log

1. Щелкните правой кнопкой мыши файл app.config в **обозревателе решений** и выберите команду **Открыть**.

     -или-

     Если есть файл app.config:

    1. В меню **Проект** выберите пункт **Добавить новый элемент**.

    2. В диалоговом окне **Добавление нового элемента** выберите элемент **Файл конфигурации приложения**.

    3. Нажмите кнопку **Добавить**.

2. Найдите раздел `<listeners>` в разделе `<source>` с атрибутом `name` , равным DefaultSource, в разделе `<sources>` . Раздел `<sources>` находится в разделе `<system.diagnostics>` в разделе `<configuration>` верхнего уровня.

3. Добавьте этот элемент в раздел `<listeners>`:

    ```xml
    <add name="SimpleLog" />
    ```

4. Найдите раздел `<sharedListeners>` в разделе `<system.diagnostics>` в разделе `<configuration>` верхнего уровня.

5. Добавьте в этот раздел `<sharedListeners>` следующий элемент:

    ```xml
    <add name="SimpleLog" type="SimpleLogStrongName" />
    ```

     Изменить значение `SimpleLogStrongName` на строгое имя прослушивателя.

## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- [Работа с журналами приложения](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)
- [Практическое руководство. Исплючения журналов](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md)
- [Практическое руководство. Запись сообщений в журнал](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md)
- [Пошаговое руководство: Изменение места записи сведений для My.Application.Log](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md)
