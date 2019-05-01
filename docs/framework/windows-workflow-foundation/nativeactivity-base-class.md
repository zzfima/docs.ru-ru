---
title: Базовый класс NativeActivity
ms.date: 03/30/2017
ms.assetid: 254a4c50-425b-426d-a32f-0f7234925bac
ms.openlocfilehash: f718d247e7110b46cdd13038c7c93c1e45612c75
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62009985"
---
# <a name="nativeactivity-base-class"></a>Базовый класс NativeActivity

<xref:System.Activities.NativeActivity> является абстрактным классом с защищенным конструктором. Подобно <xref:System.Activities.CodeActivity>, <xref:System.Activities.NativeActivity> используется для записи принудительного поведения посредством реализации метода <xref:System.Activities.NativeActivity.Execute%2A>. В отличие от <xref:System.Activities.CodeActivity>, <xref:System.Activities.NativeActivity> имеет доступ ко всем предоставляемым функциональным возможностям среды выполнения рабочего процесса с помощью объекта <xref:System.Activities.NativeActivityContext>, передаваемого методу <xref:System.Activities.NativeActivity.Execute%2A>.

## <a name="using-nativeactivitycontext"></a>Использование NativeActivityContext
 Доступ к функциям среды выполнения рабочего процесса можно получить из метода <xref:System.Activities.NativeActivity.Execute%2A> при помощи элементов параметра `context` типа <xref:System.Activities.NativeActivityContext>. Функции, доступные посредством <xref:System.Activities.NativeActivityContext>:

- Возвращение и задание аргументов и переменных.

- Планирование дочерних действий с помощью <xref:System.Activities.NativeActivityContext.ScheduleActivity%2A>

- Прерывание выполнения действия с помощью <xref:System.Activities.NativeActivityContext.Abort%2A>.

- Отмена выполнения дочернего действия с помощью <xref:System.Activities.NativeActivityContext.CancelChild%2A> и <xref:System.Activities.NativeActivityContext.CancelChildren%2A>.

- Получение доступа к закладкам действий при помощи таких методов, как <xref:System.Activities.NativeActivityContext.CreateBookmark%2A>, <xref:System.Activities.NativeActivityContext.RemoveBookmark%2A> и <xref:System.Activities.NativeActivityContext.ResumeBookmark%2A>.

- Пользовательские функции отслеживания с использованием <xref:System.Activities.CodeActivityContext.Track%2A>.

- Получение доступа к свойствам выполнения действия и свойствам значений с помощью <xref:System.Activities.CodeActivityContext.GetProperty%2A> и <xref:System.Activities.NativeActivityContext.GetValue%2A>.

- Планирование задач и функций действий с помощью <xref:System.Activities.NativeActivityContext.ScheduleAction%2A> и <xref:System.Activities.NativeActivityContext.ScheduleFunc%2A>.

### <a name="to-create-a-custom-activity-that-inherits-from-nativeactivity"></a>Создание пользовательского действия, которое наследуется от NativeActivity

1. OpenVisual Studio 2010.

2. Выберите **файл**, **новый**, а затем **проекта**. Выберите **Workflow 4.0** под **Visual C#** в **типы проектов** затем выберите **v2010** узла. Выберите **библиотеки действий** в **шаблоны** окна. Задайте имя для нового проекта HelloActivity.

3. Щелкните правой кнопкой мыши Activity1.xaml в проекте HelloActivity и выберите **удалить**.

4. Щелкните правой кнопкой мыши проект HelloActivity и выберите **добавить**, а затем **класс**. Задайте имя для нового класса HelloActivity.cs.

5. В файле HelloActivity.cs добавьте следующие директивы `using`.

    ```csharp
    using System.Activities;
    using System.Activities.Statements;
    ```

6. Сделайте так, чтобы новый класс наследовал от действия <xref:System.Activities.NativeActivity> путем добавления базового класса к объявлению класса.

    ```csharp
    class HelloActivity : NativeActivity
    ```

7. Добавьте функциональные возможности к классу путем добавления метода <xref:System.Activities.NativeActivity.Execute%2A>.

    ```csharp
    protected override void Execute(NativeActivityContext context)
    {
        Console.WriteLine("Hello World!");
    }
    ```

8. Переопределите метод <xref:System.Activities.NativeActivity.CacheMetadata%2A> и вызовите соответствующий метод Add, чтобы сообщить среде выполнения рабочего процесса о переменных, аргументах, дочерних элементах и делегатах пользовательского действия. Дополнительные сведения см. в описании класса <xref:System.Activities.NativeActivityMetadata>.

9. Для планирования закладок используйте объект <xref:System.Activities.NativeActivityContext>. Подробные сведения о том, как создавать, планировать и возобновлять закладки, см. в разделе <xref:System.Activities.WorkflowApplicationIdleEventArgs.Bookmarks%2A>.

    ```
    protected override void Execute(NativeActivityContext context)
        {
            // Create a Bookmark and wait for it to be resumed.
            context.CreateBookmark(BookmarkName.Get(context),
                new BookmarkCallback(OnResumeBookmark));
        }
    ```