---
title: Закладки - WF
ms.date: 03/30/2017
ms.assetid: 9b51a346-09ae-455c-a70a-e2264ddeb9e2
ms.openlocfilehash: c5bd8130ee623599e80014777baf92986c3b6969
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183007"
---
# <a name="bookmarks"></a>Закладки
Закладки - это механизм, позволяющий действиям пассивно ожидать ввода, не останавливая поток рабочего процесса. Когда действие сообщает об ожидании внешнего воздействия, оно может создать закладку. Это сообщает среде выполнения, что выполнение действия не должно считаться завершенным даже в случае возвращения управления из выполняющегося в данный момент метода (создавшего закладку <xref:System.Activities.Bookmark>).  
  
## <a name="bookmark-basics"></a>Основные сведения о закладках  
 Закладка <xref:System.Activities.Bookmark> представляет точку, с которой может быть продолжено выполнение (и через которую могут быть переданы входные данные) в экземпляре рабочего процесса. Обычно закладке <xref:System.Activities.Bookmark> присваиваются имя и внешний код (ведущего приложения или расширения), используемый для продолжения работы с точки закладки с соответствующими данными. При возобновлении закладки <xref:System.Activities.Bookmark> среда выполнения рабочего процесса планирует делегат <xref:System.Activities.BookmarkCallback>, который был связан с этой закладкой <xref:System.Activities.Bookmark> на момент ее создания.  
  
## <a name="bookmark-options"></a>Параметры закладки  
 В классе <xref:System.Activities.BookmarkOptions> указывается тип создаваемой закладки <xref:System.Activities.Bookmark>. Возможны следующие (не исключающие друг друга) значения: <xref:System.Activities.BookmarkOptions.None>, <xref:System.Activities.BookmarkOptions.MultipleResume> и <xref:System.Activities.BookmarkOptions.NonBlocking>. При создании закладки <xref:System.Activities.BookmarkOptions.None>, которая будет возобновлена ровно один раз, рекомендуется использовать вариант по умолчанию <xref:System.Activities.Bookmark>. При создании закладки <xref:System.Activities.BookmarkOptions.MultipleResume>, которая может быть возобновлена несколько раз, следует использовать вариант <xref:System.Activities.Bookmark>. При создании закладки <xref:System.Activities.BookmarkOptions.NonBlocking>, которая может быть не продолжена вообще, следует использовать параметр <xref:System.Activities.Bookmark>. В отличие от закладок, созданных с использованием параметров <xref:System.Activities.BookmarkOptions> по умолчанию, закладки типа <xref:System.Activities.BookmarkOptions.NonBlocking> не мешают завершению работы действия.  
  
## <a name="bookmark-resumption"></a>Возобновление закладок  
 Закладки могут возобновляться кодом извне рабочего процесса с использованием одного из перегруженных методов <xref:System.Activities.WorkflowApplication.ResumeBookmark%2A>. В этом примере создается действие `ReadLine`. При выполнении действие `ReadLine` создает <xref:System.Activities.Bookmark>, регистрирует обратный вызов и ждет возобновления чтения с закладки <xref:System.Activities.Bookmark>. После возобновления чтения с закладки действие `ReadLine` присваивает данные, переданные с закладкой <xref:System.Activities.Bookmark>, своему аргументу <xref:System.Activities.Activity%601.Result%2A>.  
  
```csharp  
public sealed class ReadLine : NativeActivity<string>  
{  
    [RequiredArgument]  
    public  InArgument<string> BookmarkName { get; set; }  
  
    protected override void Execute(NativeActivityContext context)  
    {  
        // Create a Bookmark and wait for it to be resumed.  
        context.CreateBookmark(BookmarkName.Get(context),
            new BookmarkCallback(OnResumeBookmark));  
    }  
  
    // NativeActivity derived activities that do asynchronous operations by calling
    // one of the CreateBookmark overloads defined on System.Activities.NativeActivityContext
    // must override the CanInduceIdle property and return true.  
    protected override bool CanInduceIdle  
    {  
        get { return true; }  
    }  
  
    public void OnResumeBookmark(NativeActivityContext context, Bookmark bookmark, object obj)  
    {  
        // When the Bookmark is resumed, assign its value to  
        // the Result argument.  
        Result.Set(context, (string)obj);  
    }  
}  
```  
  
 В следующем примере создается рабочий процесс, использующий действие `ReadLine` для получения имени пользователя и его отображения в окне консоли. Ведущее приложение выполняет действительную работу по сбору входных данных и передает их в рабочий процесс, возобновляя закладку <xref:System.Activities.Bookmark>.  
  
```csharp  
Variable<string> name = new Variable<string>  
{  
    Name = "name"  
};  
  
Activity wf = new Sequence  
{  
    Variables =  
    {  
        name  
    },  
    Activities =  
    {  
        new WriteLine()  
        {  
            Text = "What is your name?"  
        },  
        new ReadLine()  
        {  
            BookmarkName = "UserName",  
            Result = name  
        },  
        new WriteLine()  
        {  
            Text = new InArgument<string>((env) => "Hello, " + name.Get(env))  
        }  
    }  
};  
  
AutoResetEvent syncEvent = new AutoResetEvent(false);  
  
// Create the WorkflowApplication using the desired  
// workflow definition.  
WorkflowApplication wfApp = new WorkflowApplication(wf);  
  
// Handle the desired lifecycle events.  
wfApp.Completed = delegate(WorkflowApplicationCompletedEventArgs e)  
{  
    // Signal the host that the workflow is complete.  
    syncEvent.Set();  
};  
  
// Start the workflow.  
wfApp.Run();  
  
// Collect the user's name and resume the bookmark.  
// Bookmark resumption only occurs when the workflow  
// is idle. If a call to ResumeBookmark is made and the workflow  
// is not idle, ResumeBookmark blocks until the workflow becomes  
// idle before resuming the bookmark.  
wfApp.ResumeBookmark("UserName", Console.ReadLine());  
  
// Wait for Completed to arrive and signal that  
// the workflow is complete.  
syncEvent.WaitOne();  
```  
  
 При выполнении действие `ReadLine` создает закладку <xref:System.Activities.Bookmark> с именем `UserName` и ждет возобновления чтения с этой закладки. Узел собирает необходимые данные и возобновляет чтение с закладки <xref:System.Activities.Bookmark>. Рабочий процесс возобновляется, отображает имя и затем завершается. Следует заметить, что для возобновления закладки не требуется наличие кода синхронизации. Закладка <xref:System.Activities.Bookmark> может быть возобновлена только при простое рабочего процесса; если рабочий процесс не простаивает, вызов <xref:System.Activities.WorkflowApplication.ResumeBookmark%2A> блокируется, пока рабочий процесс не перейдет в состояние простоя.  
  
## <a name="bookmark-resumption-result"></a>Результат возобновления закладки  
 <xref:System.Activities.WorkflowApplication.ResumeBookmark%2A> возвращает значение перечисления <xref:System.Activities.BookmarkResumptionResult>, сообщая о результате выполнения запроса возобновления закладки. Возможны следующие возвращаемые значения: <xref:System.Activities.BookmarkResumptionResult.Success>, <xref:System.Activities.BookmarkResumptionResult.NotReady> и <xref:System.Activities.BookmarkResumptionResult.NotFound>. Ведущие приложения и расширения могут использовать эти значения для определения дальнейших действий.
