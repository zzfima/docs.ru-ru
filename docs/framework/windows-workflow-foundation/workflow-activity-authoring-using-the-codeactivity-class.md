---
title: "Разработка действий рабочих процессов с помощью класса CodeActivity"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cfe315c1-f86d-43ec-b9ce-2f8c469b1106
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2daec260c1224cd81280c6bf699b70efc2072588
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="workflow-activity-authoring-using-the-codeactivity-class"></a>Разработка действий рабочих процессов с помощью класса CodeActivity
Действия, созданные путем наследования от <xref:System.Activities.CodeActivity>, могут реализовывать базовое императивное поведение путем переопределения метода <xref:System.Activities.CodeActivity.Execute%2A>.  
  
## <a name="using-codeactivitycontext"></a>Использование CodeActivityContext  
 Доступ к функциям среды выполнения рабочего процесса можно получить из метода <xref:System.Activities.CodeActivity.Execute%2A> при помощи элементов параметра `context` типа <xref:System.Activities.CodeActivityContext>. Функции, доступные посредством <xref:System.Activities.CodeActivityContext>:  
  
-   Возврат и задание значений аргументов и переменных.  
  
-   Пользовательские функции отслеживания с использованием <xref:System.Activities.CodeActivityContext.Track%2A>.  
  
-   Доступ к свойствам выполнения действия с помощью <xref:System.Activities.CodeActivityContext.GetProperty%2A>.  
  
#### <a name="to-create-a-custom-activity-that-inherits-from-codeactivity"></a>Создание настраиваемого действия, которое наследуется от CodeActivity  
  
1.  Откройте [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].  
  
2.  Выберите **файл**, **новый**, а затем **проекта**. Выберите **Workflow 4.0** под **Visual C#** в **типы проектов** затем выберите **v2010** узла. Выберите **библиотеки действий** в **шаблоны** окна. Задайте имя для нового проекта HelloActivity.  
  
3.  Щелкните правой кнопкой мыши файл Activity1.xaml в проекте HelloActivity и выберите **удалить**.  
  
4.  Щелкните правой кнопкой мыши в проекте HelloActivity и выберите **добавить** , а затем **класса**. Задайте имя для нового класса HelloActivity.cs.  
  
5.  В файле HelloActivity.cs добавьте следующие директивы `using`.  
  
    ```csharp  
    using System.Activities;  
    using System.Activities.Statements;  
    ```  
  
6.  Сделайте так, чтобы новый класс наследовал от действия <xref:System.Activities.CodeActivity> путем добавления базового класса к объявлению класса.  
  
    ```csharp  
    class HelloActivity : CodeActivity  
    ```  
  
7.  Добавьте функциональные возможности к классу путем добавления метода <xref:System.Activities.CodeActivity.Execute%2A>.  
  
    ```csharp  
    protected override void Execute(CodeActivityContext context)  
    {  
        Console.WriteLine("Hello World!");  
    }  
    ```  
  
8.  Используйте объект <xref:System.Activities.CodeActivityContext> для создания записи отслеживания.  
  
    ```csharp  
    protected override void Execute(CodeActivityContext context)  
    {  
        Console.WriteLine("Hello World!");  
        CustomTrackingRecord record = new CustomTrackingRecord("MyRecord");  
        record.Data.Add(new KeyValuePair<String, Object>("ExecutionTime", DateTime.Now));  
        context.Track(record);  
    }  
    ```
