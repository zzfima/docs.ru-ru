---
title: Создание действия в среде выполнения с динамическим действием
ms.date: 03/30/2017
ms.assetid: 1af85cc6-912d-449e-90c5-c5db3eca5ace
ms.openlocfilehash: 0450a56059083f355f3fd71d95c83bf8dd1cf0e2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33515178"
---
# <a name="creating-an-activity-at-runtime-with-dynamicactivity"></a>Создание действия в среде выполнения с динамическим действием
<xref:System.Activities.DynamicActivity> представляет собой конкретный запечатанный класс с открытым конструктором. <xref:System.Activities.DynamicActivity> может использоваться для объединения функций действий во время выполнения с помощью действия DOM.  
  
## <a name="dynamicactivity-features"></a>Функции DynamicActivity  
 <xref:System.Activities.DynamicActivity> имеет доступ к свойствам, аргументам и переменным выполнения, но не имеет доступа к службам среды выполнения, таким как дочерние действия планирования и отслеживание.  
  
 Значения свойств верхнего уровня можно задавать при помощи объектов рабочих процессов <xref:System.Activities.Argument>. В императивном коде эти аргументы создаются при помощи свойств среды CLR в новом типе. На языке XAML такие аргументы объявляются при помощи тегов `x:Class` и `x:Member`.  
  
 Действия, построенные при помощи интерфейса <xref:System.Activities.DynamicActivity> в конструкторе, использующем <xref:System.ComponentModel.ICustomTypeDescriptor>. Действия, созданные в конструкторе, можно загружать динамически с помощью <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A>, как показано в следующей процедуре.  
  
#### <a name="to-create-an-activity-at-runtime-using-imperative-code"></a>Создание действия во время выполнения при помощи императивного кода  
  
1.  Откройте [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].  
  
2.  Выберите **файл**, **новый**, **проекта**. Выберите **Workflow 4.0** под **Visual C#** в **типы проектов** затем выберите **v2010** узла. Выберите **консольного приложения последовательного рабочего процесса** в **шаблоны** окна. Задайте имя для нового проекта DynamicActivitySample.  
  
3.  Щелкните правой кнопкой мыши файл Workflow1.xaml в проекте HelloActivity и выберите **удалить**.  
  
4.  Откройте файл Program.cs. Добавьте следующую директиву в начало файла.  
  
    ```  
    using System.Collections.Generic;  
    ```  
  
5.  Замените содержимое метода `Main` следующим кодом, который создаст действие <xref:System.Activities.Statements.Sequence>, содержащее отдельное действие <xref:System.Activities.Statements.WriteLine>, и назначит его свойству <xref:System.Activities.DynamicActivity.Implementation%2A> нового динамического действия.  
  
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
  
6.  Выполните приложение. Окно консоли с текстом «Hello World!» Отображает.  
  
#### <a name="to-create-an-activity-at-runtime-using-xaml"></a>Создание действия во время выполнения при помощи языка XAML  
  
1.  Откройте [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].  
  
2.  Выберите **файл**, **новый**, **проекта**. Выберите **Workflow 4.0** под **Visual C#** в **типы проектов** затем выберите **v2010** узла. Выберите **консольное приложение рабочего процесса** в **шаблоны** окна. Задайте имя для нового проекта DynamicActivitySample.  
  
3.  Откройте файл Workflow1.xaml в проекте HelloActivity. Нажмите кнопку **аргументы** в нижней части конструктора. Создайте новый аргумент `In`, вызываемый методом `TextToWrite` типа `String`.  
  
4.  Перетащите **WriteLine** действия из **примитивы** области элементов в область конструктора. Присвойте значение `TextToWrite` для **текст** свойства действия.  
  
5.  Откройте файл Program.cs. Добавьте следующую директиву в начало файла.  
  
    ```  
    using System.Activities.XamlIntegration;  
    ```  
  
6.  Замените содержимое метода `Main` следующим кодом.  
  
    ```  
    Activity act2 = ActivityXamlServices.Load(@"Workflow1.xaml");  
                    results = WorkflowInvoker.Invoke(act2, new Dictionary<string, object> { { "TextToWrite", "HelloWorld!" } });  
    Console.ReadLine();  
    ```  
  
7.  Выполните приложение. Окно консоли с текстом «Hello World!» отображается.  
  
8.  Щелкните правой кнопкой мыши файл Workflow1.xaml в **обозревателе решений** и выберите **Просмотр кода**. Следует отметить, что класс действия создается при помощи `x:Class`, а свойство - при помощи `x:Property`.  
  
## <a name="see-also"></a>См. также  
 [Разработка рабочих процессов, действий и выражений с использованием императивного кода](../../../docs/framework/windows-workflow-foundation/authoring-workflows-activities-and-expressions-using-imperative-code.md)  
 [Создание действия DynamicActivity](../../../docs/framework/windows-workflow-foundation/samples/dynamicactivity-creation.md)
