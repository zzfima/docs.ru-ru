---
title: "Практическое руководство. Запись сведений о событиях в текстовый файл (Visual Basic) | Microsoft Docs"
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
  - "журналы событий [Visual Studio], написание сведений о событии"
  - "события [Visual Basic], запись сведений о событиях в текстовый файл"
  - "текстовые файлы, запись сведений о событиях в текстовый файл"
ms.assetid: 9ca7cc03-bf99-4933-9e5e-61ee28e9a6b4
caps.latest.revision: 20
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 20
---
# Практическое руководство. Запись сведений о событиях в текстовый файл (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Объекты `My.Application.Log` и `My.Log` можно использовать для записи в журнал информации о событиях, происходящих в приложении.  В этом примере показано использование метода `My.Application.Log.WriteEntry` для записи данных трассировки в файл журнала.  
  
### Добавление и настройка прослушивателя файлового журнала  
  
1.  Щелкните правой кнопкой мыши файл app.config в **обозревателе решений** и выберите команду **Открыть**.  
  
     \- или \-  
  
     Если файл app.config отсутствует:  
  
    1.  В меню **Проект** выберите пункт **Добавить новый элемент**.  
  
    2.  В диалоговом окне **Добавление нового элемента** выберите **Файл конфигурации приложения**.  
  
    3.  Нажмите кнопку **Добавить**.  
  
2.  Найдите раздел `<listeners>` в файле конфигурации приложения.  
  
     Вы найдете раздел \<listeners\> в разделе \<source\> с именем атрибута "DefaultSource", который вложен в раздел \<System.Diagnostics\>, которой, в свою очередь, вложен в раздел верхнего уровня \<configuration\>.  
  
3.  Добавьте этот элемент в раздел `<listeners>`.  
  
    ```  
    <add name="FileLogListener" />  
    ```  
  
4.  Найдите раздел `<sharedListeners>` в разделе `<system.diagnostics>` на верхнем уровне раздела `<configuration>`.  
  
5.  Добавьте этот элемент в раздел `<sharedListeners>`.  
  
    ```  
    <add name="FileLogListener"   
        type="Microsoft.VisualBasic.Logging.FileLogTraceListener,   
              Microsoft.VisualBasic, Version=8.0.0.0, Culture=neutral,   
              PublicKeyToken=b03f5f7f11d50a3a"  
        initializeData="FileLogListenerWriter"  
        location="Custom"  
        customlocation="c:\temp\" />  
    ```  
  
     Измените значение атрибута `customlocation` на путь к каталогу журнала.  
  
    > [!NOTE]
    >  Чтобы задать значение свойства прослушивателя, используйте атрибут, имеющий то же имя, что и свойство, но со всеми строчными буквами в имени.  Например, атрибуты `location` и `customlocation` задают значения свойств<xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.Location%2A> и <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.CustomLocation%2A>.  
  
### Запись информации о событии в файловый журнал  
  
-   Для записи сведений в файл журнала используйте метод `My.Application.Log.WriteEntry` или `My.Application.Log.WriteException`.  Дополнительные сведения см. в разделах [Практическое руководство. Запись сообщений в журнал](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md) и [Практическое руководство. Запись в журнал сведений об исключениях](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md).  
  
     После настройки прослушивателя файлового журнала для сборки он получает все сообщения, которые записываются объектом `My.Application.Log` из этой сборки.  
  
## См. также  
 <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=fullName>   
 <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>   
 <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A>   
 [Работа с журналами приложения](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)   
 [Практическое руководство. Запись в журнал сведений об исключениях](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md)