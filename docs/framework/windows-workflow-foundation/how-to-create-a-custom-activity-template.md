---
title: "Как создать шаблон настраиваемого действия"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6760a5cc-6eb8-465f-b4fa-f89b39539429
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2ae81b96a348712af58c5e8527f0f04a59689368
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-create-a-custom-activity-template"></a>Как создать шаблон настраиваемого действия
Настраиваемые шаблоны действий служат для настройки конфигурации действий, в том числе настраиваемых составных действий, чтобы позволяет не создавать отдельно каждое действие и не настраивать все свойства и другие параметры вручную. Эти настраиваемые шаблоны доступны в **элементов** на [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] или в повторно размещенном конструкторе, из которого пользователи могут перетащить их в область конструктора предварительно настроенных. [!INCLUDE[wfd2](../../../includes/wfd2-md.md)]поставляется с хорошими примерами такие шаблоны: [конструктора шаблонов SendAndReceiveReply](/visualstudio/workflow-designer/sendandreceivereply-template-designer) и [конструктора шаблонов ReceiveAndSendReply](/visualstudio/workflow-designer/receiveandsendreply-template-designer) в [конструкторы действий обмена сообщениями](/visualstudio/workflow-designer/messaging-activity-designers) категории.  
  
 В первой процедуре в этом разделе описывается создание настраиваемого шаблона действий для **задержки** действия и вторая процедура кратко описывает, как сделать его доступным в [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] для проверки работы пользовательского шаблона.  
  
 В шаблонах настраиваемых действий должен быть реализован интерфейс <xref:System.Activities.Presentation.IActivityTemplateFactory>. Интерфейс имеет один метод <xref:System.Activities.Presentation.IActivityTemplateFactory.Create%2A>, с помощью которого можно создать и настроить экземпляры действий, используемые в шаблоны.  
  
### <a name="to-create-a-template-for-the-delay-activity"></a>Создание шаблона для действия Delay  
  
1.  Запустите [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].  
  
2.  На **файл** последовательно выберите пункты **New**, а затем выберите **проекта**.  
  
     Откроется диалоговое окно **Новый проект** .  
  
3.  В **типы проектов** выберите **рабочего процесса** либо из **Visual C#** проектов или **Visual Basic** группирований, в зависимости от вашей Выбор языка.  
  
4.  В **шаблоны** выберите **библиотеки действий**.  
  
5.  В **имя** введите `DelayActivityTemplate`.  
  
6.  Примите значения по умолчанию в **расположение** и **имя решения** текстовые поля и нажмите кнопку **ОК**.  
  
7.  Щелкните правой кнопкой мыши каталог ссылки на проект в окне **обозревателе решений** и выберите **добавить ссылку** Открытие **добавить ссылку** диалоговое окно.  
  
8.  Последовательно выберите пункты **.NET** и выберите **PresentationFramework** из **имя компонента** столбец слева, затем щелкните **ОК** Добавление ссылки файл PresentationFramework.dll.  
  
9. Повторите процедуру для добавления ссылок на файлы System.Activities.Presentation.dll and the WindowsBase.dll.  
  
10. Щелкните правой кнопкой мыши проект в окне **обозревателе решений** и выберите **добавить** и затем **новый элемент** Открытие **Добавление нового элемента**диалоговое окно.  
  
11. Выберите **класса** шаблона, назовите его MyDelayTemplate, затем щелкните **ОК**.  
  
12. Откройте файл MyDelayTemplate.cs и добавьте следующие инструкции.  
  
    ```  
    //Namespaces added  
    using System.Activities;  
    using System.Activities.Statements;  
    using System.Activities.Presentation;  
    using System.Windows;  
    ```  
  
13. Реализуйте метод <xref:System.Activities.Presentation.IActivityTemplateFactory> с помощью класса `MyDelayActivity` со следующим кодом. Это настраивает задержку на длительность 10 секунд.  
  
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
  
14. Выберите **построить решение** из **построения** меню, чтобы создать файл DelayActivityTemplate.dll.  
  
### <a name="to-make-the-template-available-in-a-workflow-designer"></a>Обеспечение доступности шаблона в конструкторе рабочего процесса  
  
1.  Щелкните правой кнопкой мыши решение DelayActivityTemplate **обозревателе решений** и выберите **добавить** и затем **новый проект** открыть **Добавление нового проекта** диалоговое окно.  
  
2.  Выберите **консольное приложение рабочего процесса** шаблона, назовите его `CustomActivityTemplateApp`, а затем нажмите кнопку **ОК**.  
  
3.  Щелкните правой кнопкой мыши каталог References проекта CustomActivityTemplateApp в **обозревателе решений** и выберите **добавить ссылку** Открытие **добавить ссылку** диалоговое окно поле.  
  
4.  Последовательно выберите пункты **проекты** и выберите **DelayActivityTemplate** из **имя проекта** столбец слева, затем щелкните **ОК** для добавления ссылка на файл DelayActivityTemplate.dll, созданный в первой процедуре.  
  
5.  Щелкните правой кнопкой мыши проект CustomActivityTemplateApp **обозревателе решений** и выберите **построения** для компиляции приложения.  
  
6.  Щелкните правой кнопкой мыши проект CustomActivityTemplateApp **обозревателе решений** и выберите **Назначить запускаемым проектом**.  
  
7.  Выберите **Запуск без отладки** из **отладки** меню и нажмите любую клавишу для продолжения при появлении запроса в окне cmd.exe.  
  
8.  Откройте файл Workflow1.xaml и откройте **элементов**.  
  
9. Найдите **MyDelayActivity** шаблона в **DelayActivityTemplate** категории. Перетащите его в область конструктора. Убедитесь в **свойства** окна, `Duration` свойство значение 10 секунд.  
  
## <a name="example"></a>Пример  
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
  
## <a name="see-also"></a>См. также  
 <xref:System.Activities.Presentation.IActivityTemplateFactory>  
 [Настройка конструктора рабочих процессов](../../../docs/framework/windows-workflow-foundation/customizing-the-workflow-design-experience.md)
