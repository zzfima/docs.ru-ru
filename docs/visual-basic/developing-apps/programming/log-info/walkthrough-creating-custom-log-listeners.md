---
title: "Создание пользовательских прослушивателей журнала (Visual Basic) | Документы Майкрософт"
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
- custom log listeners
- My.Application.Log object, custom log listeners
ms.assetid: 0e019115-4b25-4820-afb1-af8c6e391698
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
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
ms.openlocfilehash: 98cec8d5077e777f18c18ad1af0040b3359151f7
ms.lasthandoff: 03/13/2017

---
# <a name="walkthrough-creating-custom-log-listeners-visual-basic"></a>Пошаговое руководство. Создание пользовательских прослушивателей журнала (Visual Basic)
В этом пошаговом руководстве демонстрируется создание пользовательского прослушивателя журнала и его настройка на прослушивание выходных данных объекта `My.Application.Log`.  
  
## <a name="getting-started"></a>Начало работы  
 Прослушиватели журнала должны наследовать от класса <xref:System.Diagnostics.TraceListener>класса.  
  
#### <a name="to-create-the-listener"></a>Создание прослушивателя  
  
-   В приложении создайте класс `SimpleListener`, наследуемый от класса <xref:System.Diagnostics.TraceListener>.  
  
     [!code-vb[VbVbalrMyApplicationLog#16](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/walkthrough-creating-custom-log-listeners_1.vb)]  
  
     Методы <xref:System.Diagnostics.TraceListener.Write%2A> и <xref:System.Diagnostics.TraceListener.WriteLine%2A>, требуемые базовым классом, вызывают функцию `MsgBox` для отображения входных данных.  
  
     Атрибут <xref:System.Security.Permissions.HostProtectionAttribute> применяется к методам <xref:System.Diagnostics.TraceListener.Write%2A> и <xref:System.Diagnostics.TraceListener.WriteLine%2A> таким образом, чтобы их атрибуты соответствовали методам базового класса. Атрибут <xref:System.Security.Permissions.HostProtectionAttribute> позволяет узлу, на котором выполняется код, определять, что код обеспечивает синхронизацию защиты узла.  
  
    > [!NOTE]
    >  Атрибут <xref:System.Security.Permissions.HostProtectionAttribute> действует только для неуправляемых приложений, на которых размещена среда CLR и которые реализуют защиту узлов, таких как SQL Server.  
  
 Чтобы объект `My.Application.Log` использовал прослушиватель журнала, следует присвоить строгое имя сборке, содержащей прослушиватель журнала.  
  
 В следующей процедуре показано несколько простых шагов по созданию сборки прослушивателя журнала со строгим именем. Дополнительные сведения см. в разделе [Создание и использование сборок со строгими именами](https://msdn.microsoft.com/library/xwb8f617).  
  
#### <a name="to-strongly-name-the-log-listener-assembly"></a>Задание строгого имени сборке прослушивателя журнала  
  
1.  Выберите проект в **Обозревателе решений**. В меню **Проект** выберите пункт **Свойства**. Дополнительные сведения см. в разделе [Знакомство с конструктором проектов](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).  
  
2.  Откройте вкладку **Подписывание**.  
  
3.  Выберите поле **Подписать сборку**.  
  
4.  В раскрывающемся списке **Выберите файл ключа строгого имени** щелкните **\<Новый...>**.  
  
     Откроется диалоговое окно **Создание ключа строгого имени**.  
  
5.  Укажите имя для файла ключа в поле **Имя файла ключа**.  
  
6.  Введите пароль в поля **Введите пароль** и **Подтверждение пароля**.  
  
7.  Нажмите кнопку **ОК**.  
  
8.  Перестройте приложение.  
  
## <a name="adding-the-listener"></a>Добавление прослушивателя  
 Теперь, когда сборка имеет строгое имя, необходимо определить строгое имя прослушивателя, чтобы объект `My.Application.Log` использовал прослушиватель журнала.  
  
 Тип со строгим именем имеет следующий формат:  
  
 \<имя типа>, \<имя сборки>, \<номер версии>, \<язык>, \<строгое имя>  
  
#### <a name="to-determine-the-strong-name-of-the-listener"></a>Определение строгого имени прослушивателя  
  
-   В следующем коде показано, как определить строгое имя типа для `SimpleListener`.  
  
     [!code-vb[VbVbalrMyApplicationLog#17](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/walkthrough-creating-custom-log-listeners_2.vb)]  
  
     Строгое имя типа зависит от проекта.  
  
 Можно добавить прослушиватель со строгим именем в коллекцию прослушивателей журнала `My.Application.Log`.  
  
#### <a name="to-add-the-listener-to-myapplicationlog"></a>Добавление прослушивателя в My.Application.Log  
  
1.  Щелкните правой кнопкой мыши файл app.config в **обозревателе решений** и выберите команду **Открыть**.  
  
     -или-  
  
     Если есть файл app.config:  
  
    1.  В меню **Проект** выберите пункт **Добавить новый элемент**.  
  
    2.  В диалоговом окне **Добавление нового элемента** выберите элемент **Файл конфигурации приложения**.  
  
    3.  Нажмите кнопку **Добавить**.  
  
2.  Найдите раздел `<listeners>` в разделе `<source>` с атрибутом `name` , равным DefaultSource, в разделе `<sources>` . Раздел `<sources>` находится в разделе `<system.diagnostics>` в разделе `<configuration>` верхнего уровня.  
  
3.  Добавьте этот элемент в раздел `<listeners>`:  
  
    ```  
    <add name="SimpleLog" />  
    ```  
  
4.  Найдите раздел `<sharedListeners>` в разделе `<system.diagnostics>` в разделе `<configuration>` верхнего уровня.  
  
5.  Добавьте в этот раздел `<sharedListeners>` следующий элемент:  
  
    ```  
    <add name="SimpleLog" type="SimpleLogStrongName" />  
    ```  
  
     Изменить значение `SimpleLogStrongName` на строгое имя прослушивателя.  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=fullName>   
 [Работа с журналами приложения](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)   
 [Практическое руководство. Запись в журнал сведений об исключениях](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md)   
 [Практическое руководство. Запись сообщений в журнал](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md)   
 [Пошаговое руководство. Изменение места записи сведений для My.Application.Log](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md)
