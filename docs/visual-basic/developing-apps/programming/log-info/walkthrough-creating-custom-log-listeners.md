---
title: "Пошаговое руководство. Создание пользовательских прослушивателей журнала (Visual Basic) | Microsoft Docs"
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
  - "пользовательские слушатели журнала"
  - "My.Application.Log - объект, пользовательские слушатели журнала"
ms.assetid: 0e019115-4b25-4820-afb1-af8c6e391698
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# Пошаговое руководство. Создание пользовательских прослушивателей журнала (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

В этом пошаговом руководстве демонстрируется порядок создания пользовательского прослушивателя журнала и его настройки для прослушивания вывода объекта `My.Application.Log`.  
  
## Начало работы  
 Прослушиватели журнала должны быть наследниками класса <xref:System.Diagnostics.TraceListener>.  
  
#### Чтобы создать прослушиватель  
  
-   В приложении создайте класс `SimpleListener`, наследуемый от класса <xref:System.Diagnostics.TraceListener>.  
  
     [!code-vb[VbVbalrMyApplicationLog#16](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/visualbasic/VbVbalrMyApplicationLog/Form1.vb#16)]  
  
     Методы <xref:System.Diagnostics.TraceListener.Write%2A> и <xref:System.Diagnostics.TraceListener.WriteLine%2A>, требуемые базовым классом, вызывают функцию `MsgBox` для отображения входных данных.  
  
     Атрибут <xref:System.Security.Permissions.HostProtectionAttribute> применяется к методам <xref:System.Diagnostics.TraceListener.Write%2A> и <xref:System.Diagnostics.TraceListener.WriteLine%2A> таким образом, чтобы их атрибуты соответствовали методам базового класса.  Атрибут <xref:System.Security.Permissions.HostProtectionAttribute> позволяет узлу, на котором выполняется код, знать, что код обеспечивает синхронизацию защиты узла.  
  
    > [!NOTE]
    >  Атрибут <xref:System.Security.Permissions.HostProtectionAttribute> применяется только для неуправляемых приложений, на которых размещена среда CLR и которые реализуют защиту узлов, таких как SQL Server.  
  
 Чтобы обеспечить использование объектом `My.Application.Log` этого прослушивателя журнала, следует присвоить строгое имя сборке, содержащей прослушиватель журнала.  
  
 В следующей процедуре продемонстрировано несколько простых шагов по созданию сборки прослушивателя журнала со строгим именем.  Дополнительные сведения см. в разделе [Создание и использование сборок со строгими именами](../Topic/Creating%20and%20Using%20Strong-Named%20Assemblies.md).  
  
#### Чтобы присвоить строгое имя сборке прослушивателя журнала  
  
1.  Выберите проект в **обозревателе решений**.  В меню **Проект** выберите пункт **Свойства**.  Дополнительные сведения см. в разделе [Introduction to the Project Designer](http://msdn.microsoft.com/ru-ru/898dd854-c98d-430c-ba1b-a913ce3c73d7).  
  
2.  Выберите вкладку **Подпись**.  
  
3.  Выберите поле **Подписать сборку**.  
  
4.  В списке **Выберите файл ключей строгого имени** выберите пункт **\<Создать\>**.  
  
     Появится диалоговое окно **Создание ключа строгого имени**.  
  
5.  Укажите имя для файла ключа в поле **Имя файла ключей**.  
  
6.  Введите пароль в поля **Вводите пароль** и **Подтверждение пароля**.  
  
7.  Нажмите кнопку **ОК**.  
  
8.  Перестройте приложение.  
  
## Добавление прослушивателя  
 Теперь, когда сборка имеет строгое имя, необходимо определить строгое имя прослушивателя с тем, чтобы объект `My.Application.Log` использовал прослушиватель журнала.  
  
 Тип со строгим именем имеет следующий формат:  
  
 \<имя типа\>, \<имя сборки\>, \<номер версии\>, \<язык\>, \<строгое имя\>  
  
#### Чтобы определить строгое имя прослушивателя  
  
-   В следующем коде показано, как определить строгое имя типа для `SimpleListener`.  
  
     [!code-vb[VbVbalrMyApplicationLog#17](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/visualbasic/VbVbalrMyApplicationLog/Form1.vb#17)]  
  
     Строгое имя типа зависит от проекта.  
  
 Можно добавить прослушиватель со строгим именем в коллекцию прослушивателей журнала `My.Application.Log`.  
  
#### Чтобы добавить прослушиватель в коллекцию My.Application.Log  
  
1.  Щелкните правой кнопкой мыши файл app.config в **обозревателе решений** и выберите команду **Открыть**.  
  
     \-или\-  
  
     Если есть файл app.config:  
  
    1.  В меню **Проект** выберите пункт **Добавить новый элемент**.  
  
    2.  В диалоговом окне **Добавление нового элемента** выберите **Файл конфигурации приложения**.  
  
    3.  Нажмите кнопку **Добавить**.  
  
2.  Найдите раздел `<listeners>` в разделе `<source>` с атрибутом `name`, равным "DefaultSource", в разделе `<sources>`.  Раздел `<sources>` находится в разделе `<system.diagnostics>` на верхнем уровне раздела `<configuration>`.  
  
3.  Добавьте этот элемент в раздел `<listeners>`.  
  
    ```  
    <add name="SimpleLog" />  
    ```  
  
4.  Найдите раздел `<sharedListeners>` в разделе `<system.diagnostics>` на верхнем уровне раздела `<configuration>`.  
  
5.  Добавьте этот элемент в раздел `<sharedListeners>`.  
  
    ```  
    <add name="SimpleLog" type="SimpleLogStrongName" />  
    ```  
  
     Измените значение `SimpleLogStrongName` на строгое имя прослушивателя.  
  
## См. также  
 <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=fullName>   
 [Работа с журналами приложения](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)   
 [Практическое руководство. Запись в журнал сведений об исключениях](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md)   
 [Практическое руководство. Запись сообщений в журнал](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md)   
 [Пошаговое руководство. Изменение места записи информации для My.Application.Log](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md)