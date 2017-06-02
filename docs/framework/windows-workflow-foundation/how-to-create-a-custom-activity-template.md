---
title: "Как создать шаблон настраиваемого действия | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6760a5cc-6eb8-465f-b4fa-f89b39539429
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# Как создать шаблон настраиваемого действия
Настраиваемые шаблоны действий служат для настройки конфигурации действий, в том числе настраиваемых составных действий, чтобы позволяет не создавать отдельно каждое действие и не настраивать все свойства и другие параметры вручную.Эти настраиваемые шаблоны могут быть сделаны доступными в **области элементов** в [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] или в повторно размещенном конструкторе, из которого пользователи могут перетащить их в предварительно настроенную область конструктора.[!INCLUDE[wfd2](../../../includes/wfd2-md.md)] поставляется с хорошими примерами таких шаблонов: [Конструктор шаблона SendAndReceiveReply](../Topic/SendAndReceiveReply%20Template%20Designer.md) и [Конструктор шаблона ReceiveAndSendReply](../Topic/ReceiveAndSendReply%20Template%20Designer.md) в категории [Конструкторы действий обмена сообщениями](../Topic/Messaging%20Activity%20Designers.md).  
  
 Первая процедура в этом подразделе описывает способ создания настраиваемого шаблона действий для действия **Delay**, а вторая процедура кратко описывает, как сделать его доступным в объекте [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] для проверки, что настраиваемый шаблон работает.  
  
 В шаблонах настраиваемых действий должен быть реализован интерфейс <xref:System.Activities.Presentation.IActivityTemplateFactory>.Интерфейс имеет один метод <xref:System.Activities.Presentation.IActivityTemplateFactory.Create%2A>, с помощью которого можно создать и настроить экземпляры действий, используемые в шаблоны.  
  
### Создание шаблона для действия Delay  
  
1.  Запустите среду [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].  
  
2.  В меню **Файл** последовательно выберите команды **Создать** и **Проект**.  
  
     Откроется диалоговое окно **Новый проект**.  
  
3.  В области **Типы проектов** выберите категорию **Рабочий процесс** из групп проектов **Visual C\#** или **Visual Basic** \(в зависимости от языка программирования\).  
  
4.  В области **Шаблоны** выберите **Библиотека действий**.  
  
5.  В поле **Имя** введите `DelayActivityTemplate`.  
  
6.  Оставьте значения по умолчанию текстовых полей **Расположение** и **Имя решения**, затем нажмите кнопку **ОК**.  
  
7.  В **обозревателе решений** щелкните правой кнопкой мыши папку References проекта DelayActivityTemplate и выберите команду **Добавить ссылку**, чтобы открыть диалоговое окно **Добавление ссылки**.  
  
8.  Перейдите на вкладку **.NET** и выберите **PresentationFramework** из столбца **Имя компонента** слева, затем нажмите кнопку **ОК**, чтобы добавить ссылку на файл PresentationFramework.dll.  
  
9. Повторите процедуру для добавления ссылок на файлы System.Activities.Presentation.dll and the WindowsBase.dll.  
  
10. Щелкните правой кнопкой мыши проект в окне **Обозреватель решений**, укажите пункт **Добавить** и выберите пункт **Новый элемент**, чтобы открыть диалоговое окно **Добавление нового элемента**.  
  
11. Выберите шаблон **Class**, назовите его MyDelayTemplate, затем нажмите кнопку **ОК**.  
  
12. Откройте файл MyDelayTemplate.cs и добавьте следующие инструкции.  
  
    ```  
  
    //Namespaces added  
    using System.Activities;  
    using System.Activities.Statements;  
    using System.Activities.Presentation;  
    using System.Windows;  
  
    ```  
  
13. Реализуйте метод <xref:System.Activities.Presentation.IActivityTemplateFactory> с помощью класса `MyDelayActivity` со следующим кодом.Это настраивает задержку на длительность 10 секунд.  
  
    ```  
  
    public sealed class MyDelayActivity : IActivityTemplateFactory  
    {  
        public Activity Create(System.Windows.DependencyObject target)  
        {  
            return new System.Activities.Statements.Delay  
            {  
                DisplayName = "DelayActivityTemplate",  
                Duration = new TimeSpan(0, 0, 10)  
  
            };  
        }  
    }  
  
    ```  
  
14. Чтобы создать файл DelayActivityTemplate.dll, выберите команду **Построить решение** в меню **Построение**.  
  
### Обеспечение доступности шаблона в конструкторе рабочего процесса  
  
1.  Щелкните правой кнопкой мыши решение DelayActivityTemplate в окне **Обозреватель решений**, укажите пункт **Добавить** и выберите пункт **Новый проект**, чтобы открыть диалоговое окно **Добавление нового проекта**.  
  
2.  Выберите шаблон **Workflow Console Application**, назовите его `CustomActivityTemplateApp`, затем нажмите кнопку **ОК**.  
  
3.  В **обозревателе решений** щелкните правой кнопкой мыши папку References проекта CustomActivityTemplateApp и выберите команду **Добавить ссылку**, чтобы открыть диалоговое окно **Добавление ссылки**.  
  
4.  Перейдите на вкладку **Проекты** и выберите **DelayActivityTemplate** из столбца **Имя проекта** слева, затем нажмите кнопку **ОК**, чтобы добавить ссылку на файл DelayActivityTemplate.dll.  
  
5.  В окне **Обозреватель решений** щелкните правой кнопкой мыши проект CustomActivityTemplateApp и выберите команду **Построить**, чтобы выполнить компиляцию приложения.  
  
6.  В **обозревателе решений** щелкните правой кнопкой мыши проект CustomActivityTemplateApp и выберите команду **Установить как запускаемый проект**.  
  
7.  Выберите команду **Запустить без отладки** из меню **Отладка** и нажмите любую клавишу для продолжения, когда появится запрос в окне cmd.exe.  
  
8.  Откройте файл Workflow1.xaml и откройте **область инструментов**.  
  
9. Перейдите к шаблону **MyDelayActivity** в категории **DelayActivityTemplate**.Перетащите его в область конструктора.В окне **Свойства** подтвердите, что для свойства `Duration` установлено значение 10 секунд.  
  
## Пример  
 Теперь файл MyDelayActivity.cs должен содержать следующий код.  
  
```  
  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
  
//Namespaces added  
using System.Activities;  
using System.Activities.Statements;  
using System.Activities.Presentation;  
using System.Windows;  
  
namespace DelayActivityTemplate  
{  
    public sealed class MyDelayActivity : IActivityTemplateFactory  
    {  
        public Activity Create(System.Windows.DependencyObject target)  
        {  
            return new System.Activities.Statements.Delay  
            {  
                DisplayName = "DelayActivityTemplate",  
                Duration = new TimeSpan(0, 0, 10)  
  
            };  
        }  
    }  
}  
  
```  
  
## См. также  
 <xref:System.Activities.Presentation.IActivityTemplateFactory>   
 [Рекомендации по настройке конструктора рабочих процессов](../../../docs/framework/windows-workflow-foundation//customizing-the-workflow-design-experience.md)