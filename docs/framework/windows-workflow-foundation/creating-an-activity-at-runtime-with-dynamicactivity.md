---
title: Создание действия в среде выполнения с динамическим действием
ms.date: 03/30/2017
ms.assetid: 1af85cc6-912d-449e-90c5-c5db3eca5ace
ms.openlocfilehash: 871108fd09e9127b3f9e06174f05a47c7fd7682c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182982"
---
# <a name="creating-an-activity-at-runtime-with-dynamicactivity"></a>Создание действия в среде выполнения с динамическим действием
<xref:System.Activities.DynamicActivity> представляет собой конкретный запечатанный класс с открытым конструктором. <xref:System.Activities.DynamicActivity> может использоваться для объединения функций действий во время выполнения с помощью действия DOM.  
  
## <a name="dynamicactivity-features"></a>Возможности DynamicActivity  
 <xref:System.Activities.DynamicActivity> имеет доступ к свойствам, аргументам и переменным выполнения, но не имеет доступа к службам среды выполнения, таким как дочерние действия планирования и отслеживание.  
  
 Значения свойств верхнего уровня можно задавать при помощи объектов рабочих процессов <xref:System.Activities.Argument>. В императивном коде эти аргументы создаются при помощи свойств среды CLR в новом типе. На языке XAML такие аргументы объявляются при помощи тегов `x:Class` и `x:Member`.  
  
 Действия, построенные при помощи интерфейса <xref:System.Activities.DynamicActivity> в конструкторе, использующем <xref:System.ComponentModel.ICustomTypeDescriptor>. Действия, созданные в конструкторе, можно загружать динамически с помощью <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A>, как показано в следующей процедуре.  
  
#### <a name="to-create-an-activity-at-runtime-using-imperative-code"></a>Создание действия во время выполнения при помощи императивного кода  
  
1. OpenVisual Studio 2010.  
  
2. Выберите **файл**, **Новый**, **Проект**. Выберите **Рабочий процесс 4.0** под **Visual C в** окне типов **проекта** и выберите узло **v2010.** Выберите **консольное приложение Sequential Workflow** в окне **шаблонов.** Задайте имя для нового проекта DynamicActivitySample.  
  
3. Правонажмите Workflow1.xaml в проекте HelloActivity и выберите **Удалить**.  
  
4. Откройте файл Program.cs. Добавьте следующую директиву в начало файла.  
  
    ```csharp  
    using System.Collections.Generic;  
    ```  
  
5. Замените содержимое метода `Main` следующим кодом, который создаст действие <xref:System.Activities.Statements.Sequence>, содержащее отдельное действие <xref:System.Activities.Statements.WriteLine>, и назначит его свойству <xref:System.Activities.DynamicActivity.Implementation%2A> нового динамического действия.  
  
    ```csharp  
    //Define the input argument for the activity  
    var textOut = new InArgument<string>();  
    //Create the activity, property, and implementation  
                Activity dynamicWorkflow = new DynamicActivity()  
                {  
                    Properties =
                    {  
                        new DynamicActivityProperty  
                        {  
                            Name = "Text",  
                            Type = typeof(InArgument<String>),  
                            Value = textOut  
                        }  
                    },  
                    Implementation = () => new Sequence()  
                    {  
                        Activities =
                        {  
                            new WriteLine()  
                            {  
                                Text = new InArgument<string>(env => textOut.Get(env))  
                            }  
                        }  
                    }  
                };  
    //Execute the activity with a parameter dictionary  
                WorkflowInvoker.Invoke(dynamicWorkflow, new Dictionary<string, object> { { "Text", "Hello World!" } });  
                Console.ReadLine();  
    ```  
  
6. Запустите приложение. Консольное окно с текстом "Здравствуйте, мир!" Отображает.  
  
#### <a name="to-create-an-activity-at-runtime-using-xaml"></a>Создание действия во время выполнения при помощи языка XAML  
  
1. Открыть Visual Studio 2010.  
  
2. Выберите **файл**, **Новый**, **Проект**. Выберите **Рабочий процесс 4.0** под **Visual C в** окне типов **проекта** и выберите узло **v2010.** Выберите **консольное приложение Workflow** в окне **шаблонов.** Задайте имя для нового проекта DynamicActivitySample.  
  
3. Откройте файл Workflow1.xaml в проекте HelloActivity. Нажмите на опцию **Аргументы** в нижней части дизайнера. Создайте новый аргумент `In`, вызываемый методом `TextToWrite` типа `String`.  
  
4. Перетащите активность **WriteLine** из раздела **Primitives** в панели инструментов на поверхность дизайнера. Присвоите `TextToWrite` значение свойству **текста** действия.  
  
5. Откройте файл Program.cs. Добавьте следующую директиву в начало файла.  
  
    ```csharp  
    using System.Activities.XamlIntegration;  
    ```  
  
6. Замените содержимое метода `Main` следующим кодом.  
  
    ```csharp  
    Activity act2 = ActivityXamlServices.Load(@"Workflow1.xaml");  
                    results = WorkflowInvoker.Invoke(act2, new Dictionary<string, object> { { "TextToWrite", "HelloWorld!" } });  
    Console.ReadLine();  
    ```  
  
7. Запустите приложение. Консольное окно с текстом "Здравствуйте, мир!" Появится .  
  
8. Нажмите правой кнопкой мыши на файл Workflow1.xaml в **Solution Explorer** и выберите **Код просмотра.** Следует отметить, что класс действия создается при помощи `x:Class`, а свойство - при помощи `x:Property`.  
  
## <a name="see-also"></a>См. также раздел

- [Разработка рабочих процессов, действий и выражений с использованием императивного кода](authoring-workflows-activities-and-expressions-using-imperative-code.md)
