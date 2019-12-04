---
title: Как создать шаблон настраиваемого действия
ms.date: 03/30/2017
ms.assetid: 6760a5cc-6eb8-465f-b4fa-f89b39539429
ms.openlocfilehash: f910d1367c941dbc319421d402cae8f4194872e5
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715258"
---
# <a name="how-to-create-a-custom-activity-template"></a>Как создать шаблон настраиваемого действия

Настраиваемые шаблоны действий служат для настройки конфигурации действий, в том числе настраиваемых составных действий, чтобы позволяет не создавать отдельно каждое действие и не настраивать все свойства и другие параметры вручную. Эти пользовательские шаблоны можно сделать доступными на **панели элементов** в конструктор рабочих процессов Windows или в конструкторе, где пользователи могут перетащить их в предварительно настроенную область конструктора. Конструктор рабочих процессов поставляется с хорошим примером таких шаблонов: [конструктор шаблонов SendAndReceiveReply](/visualstudio/workflow-designer/sendandreceivereply-template-designer) и [конструктор шаблонов ReceiveAndSendReply](/visualstudio/workflow-designer/receiveandsendreply-template-designer) в категории [Конструкторы действий обмена сообщениями](/visualstudio/workflow-designer/messaging-activity-designers) .

 В первой процедуре в этом разделе описывается создание настраиваемого шаблона действия для действия **delay** , а во второй процедуре показано, как сделать ее доступной в конструктор рабочих процессов, чтобы убедиться в том, что настраиваемый шаблон работает.

 В шаблонах настраиваемых действий должен быть реализован интерфейс <xref:System.Activities.Presentation.IActivityTemplateFactory>. Интерфейс имеет один метод <xref:System.Activities.Presentation.IActivityTemplateFactory.Create%2A>, с помощью которого можно создать и настроить экземпляры действий, используемые в шаблоны.

## <a name="to-create-a-template-for-the-delay-activity"></a>Создание шаблона для действия Delay

1. Запустите Visual Studio 2010.

2. В меню **Файл** наведите указатель мыши на элемент **Создать** и выберите **Проект**.

     Откроется диалоговое окно **Новый проект** .

3. На панели **типы проектов** выберите **Рабочий процесс** из **визуальных C#**  проектов или **Visual Basic** группирований в зависимости от предпочитаемого языка.

4. В области **шаблоны** выберите пункт **Библиотека действий**.

5. В поле **имя** введите `DelayActivityTemplate`.

6. Примите значения по умолчанию в текстовых полях **Расположение** и **имя решения** и нажмите кнопку **ОК**.

7. Щелкните правой кнопкой мыши каталог References проекта Делайактивититемплате в **Обозреватель решений** и выберите команду **Добавить ссылку** , чтобы открыть диалоговое окно **Добавление ссылки** .

8. Перейдите на вкладку **.NET** и выберите **PresentationFramework** в столбце **имя компонента** слева и нажмите кнопку **ОК** , чтобы добавить ссылку на файл PresentationFramework. dll.

9. Повторите процедуру для добавления ссылок на файлы System.Activities.Presentation.dll and the WindowsBase.dll.

10. Щелкните правой кнопкой мыши проект Делайактивититемплате в **Обозреватель решений** и выберите **Добавить** , а затем **новый элемент** , чтобы открыть диалоговое окно **Добавление нового элемента** .

11. Выберите шаблон **класса** , назовите его миделайтемплате и нажмите кнопку **ОК**.

12. Откройте файл MyDelayTemplate.cs и добавьте следующие инструкции.

    ```csharp
    //Namespaces added
    using System.Activities;
    using System.Activities.Statements;
    using System.Activities.Presentation;
    using System.Windows;
    ```

13. Реализуйте метод <xref:System.Activities.Presentation.IActivityTemplateFactory> с помощью класса `MyDelayActivity` со следующим кодом. Это настраивает задержку на длительность 10 секунд.

    ```csharp
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

14. В меню **Сборка** выберите пункт **собрать решение** , чтобы создать файл делайактивититемплате. dll.

### <a name="to-make-the-template-available-in-a-workflow-designer"></a>Обеспечение доступности шаблона в конструкторе рабочего процесса

1. Щелкните правой кнопкой мыши решение Делайактивититемплате в **Обозреватель решений** и выберите **Добавить** , а затем — **создать проект** , чтобы открыть диалоговое окно **Добавление нового проекта** .

2. Выберите шаблон **консольное приложение рабочего процесса** , назовите его `CustomActivityTemplateApp`и нажмите кнопку **ОК**.

3. Щелкните правой кнопкой мыши каталог References проекта Кустомактивититемплатеапп в **Обозреватель решений** и выберите команду **Добавить ссылку** , чтобы открыть диалоговое окно **Добавление ссылки** .

4. Перейдите на вкладку **проекты** и выберите **Делайактивититемплате** в столбце **имя проекта** слева и нажмите кнопку **ОК** , чтобы добавить ссылку на файл делайактивититемплате. dll, созданный в первой процедуре.

5. Щелкните правой кнопкой мыши проект Кустомактивититемплатеапп в **Обозреватель решений** и выберите **Build (собрать** ), чтобы скомпилировать приложение.

6. Щелкните правой кнопкой мыши проект Кустомактивититемплатеапп в **Обозреватель решений** и выберите пункт **Назначить запускаемым проектом**.

7. Выберите **Запуск без отладки** в меню **Отладка** и нажмите любую клавишу, чтобы продолжить при появлении запроса в окне cmd. exe.

8. Откройте файл Workflow1. XAML и откройте **панель элементов**.

9. Откройте шаблон **миделайактивити** в категории **делайактивититемплате** . Перетащите его в область конструктора. В окне **Свойства** подтвердите, что для свойства `Duration` установлено значение 10 секунд.

## <a name="example"></a>Пример
 Теперь файл MyDelayActivity.cs должен содержать следующий код.

```csharp
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

## <a name="see-also"></a>См. также:

- <xref:System.Activities.Presentation.IActivityTemplateFactory>
- [Настройка конструктора рабочих процессов](customizing-the-workflow-design-experience.md)
