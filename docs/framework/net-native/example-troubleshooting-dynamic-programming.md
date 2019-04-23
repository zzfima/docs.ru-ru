---
title: Пример Устранение неполадок динамического программирования
ms.date: 03/30/2017
ms.assetid: 42ed860a-a022-4682-8b7f-7c9870784671
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: af71c4916a2abdeb019e538a33ad05efa727e720
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59137895"
---
# <a name="example-troubleshooting-dynamic-programming"></a><span data-ttu-id="de398-102">Пример Устранение неполадок динамического программирования</span><span class="sxs-lookup"><span data-stu-id="de398-102">Example: Troubleshooting Dynamic Programming</span></span>
> [!NOTE]
>  <span data-ttu-id="de398-103">В этом разделе рассматривается предварительная версия программного обеспечения для разработчиков машинного кода .NET.</span><span class="sxs-lookup"><span data-stu-id="de398-103">This topic refers to the .NET Native Developer Preview, which is pre-release software.</span></span> <span data-ttu-id="de398-104">Предварительную версию можно скачать на [веб-сайте Microsoft Connect](https://go.microsoft.com/fwlink/?LinkId=394611) (требуется регистрация).</span><span class="sxs-lookup"><span data-stu-id="de398-104">You can download the preview from the [Microsoft Connect website](https://go.microsoft.com/fwlink/?LinkId=394611) (requires registration).</span></span>  
  
 <span data-ttu-id="de398-105">Не все метаданных поиска ошибок в приложениях, разработанных с использованием цепочки инструментов [!INCLUDE[net_native](../../../includes/net-native-md.md)], приводят к исключению.</span><span class="sxs-lookup"><span data-stu-id="de398-105">Not all metadata lookup failures in apps developed using the [!INCLUDE[net_native](../../../includes/net-native-md.md)] tool chain result in an exception.</span></span>  <span data-ttu-id="de398-106">Некоторые могут проявляться в непредсказуемом виде в приложении.</span><span class="sxs-lookup"><span data-stu-id="de398-106">Some can manifest in unpredictable ways in an app.</span></span>  <span data-ttu-id="de398-107">В следующем примере показано нарушение доступа, вызванное ссылкой на пустой объект:</span><span class="sxs-lookup"><span data-stu-id="de398-107">The following example shows an access violation caused by referencing a null object:</span></span>  
  
```  
Access violation - code c0000005 (first chance)  
App!$3_App::Core::Util::NavigationArgs.Setup  
App!$3_App::Core::Util::NavigationArgs..ctor  
App!$0_App::Gibbon::Util::DesktopNavigationArgs..ctor  
App!$0_App::ViewModels::DesktopAppVM.NavigateToPage  
App!$3_App::Core::ViewModels::AppViewModel.NavigateToFirstPage  
App!$3_App::Core::ViewModels::AppViewModel::<HandleLaunch>d__a.MoveNext  
App!$43_System::Runtime::CompilerServices::AsyncMethodBuilderCore.CallMoveNext  
App!System::Action.InvokeClosedStaticThunk  
App!System::Action.Invoke  
App!$43_System::Threading::Tasks::AwaitTaskContinuation.InvokeAction  
App!$43_System::Threading::SendOrPostCallback.InvokeOpenStaticThunk  
[snip]  
```  
  
 <span data-ttu-id="de398-108">Давайте попробуем устранить данное исключение, используя трехшаговый подход, описанный в подразделе "Устранение вручную проблем с отсутствующими метаданными" раздела [Начало работы](../../../docs/framework/net-native/getting-started-with-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="de398-108">Let's try to troubleshoot this exception by using the three-step approach outlined in the "Manually resolve missing metadata" section of [Getting Started](../../../docs/framework/net-native/getting-started-with-net-native.md).</span></span>  
  
## <a name="what-was-the-app-doing"></a><span data-ttu-id="de398-109">Что делало это приложение?</span><span class="sxs-lookup"><span data-stu-id="de398-109">What was the app doing?</span></span>  
 <span data-ttu-id="de398-110">В первую очередь следует отметить механизм обработки ключевого слова `async` в начале стека.</span><span class="sxs-lookup"><span data-stu-id="de398-110">The first thing to note is the `async` keyword machinery at the base of the stack.</span></span>  <span data-ttu-id="de398-111">Определить, что приложение действительно делало в методе `async` может быть проблематично, так как стек потерял контекст исходного вызова и выполнял код `async` в другом потоке.</span><span class="sxs-lookup"><span data-stu-id="de398-111">Determining what the app was really doing in an `async` method can be problematic, because the stack has lost the context of the originating call and has run the `async` code on a different thread.</span></span> <span data-ttu-id="de398-112">Тем не менее, мы можем предположить, что приложение пытается загрузить свою первую страницу.</span><span class="sxs-lookup"><span data-stu-id="de398-112">However, we can deduce that the app is trying to load its first page.</span></span>  <span data-ttu-id="de398-113">В реализации для `NavigationArgs.Setup` нарушение доступа было вызвано следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="de398-113">In the implementation for `NavigationArgs.Setup`, the following code caused the access violation:</span></span>  
  
```  
AppViewModel.Current.LayoutVM.PageMap  
```  
  
 <span data-ttu-id="de398-114">В этом случае свойство `LayoutVM` для `AppViewModel.Current` имело значение **NULL**.</span><span class="sxs-lookup"><span data-stu-id="de398-114">In this instance, the `LayoutVM` property on `AppViewModel.Current` was **null**.</span></span>  <span data-ttu-id="de398-115">Отсутствие некоторых метаданных вызвало небольшую разницу в поведении и привело к инициализации свойства вместо набора, как ожидало приложение.</span><span class="sxs-lookup"><span data-stu-id="de398-115">Some absence of metadata caused a subtle behavior difference and resulted in a property being uninitialized instead of set, as the app expected.</span></span>  <span data-ttu-id="de398-116">Задание точки останова в коде, в котором должно было быть реализовано `LayoutVM`, может пролить свет на ситуацию.</span><span class="sxs-lookup"><span data-stu-id="de398-116">Setting a breakpoint in the code where `LayoutVM` should have been initialized might throw light on the situation.</span></span>  <span data-ttu-id="de398-117">Тем не менее, обратите внимание, что типом `LayoutVM` является `App.Core.ViewModels.Layout.LayoutApplicationVM`.</span><span class="sxs-lookup"><span data-stu-id="de398-117">However, note that `LayoutVM`’s type is `App.Core.ViewModels.Layout.LayoutApplicationVM`.</span></span>  <span data-ttu-id="de398-118">Единственной директивой метаданных, присутствующей в файле rd.xml на настоящий момент, является:</span><span class="sxs-lookup"><span data-stu-id="de398-118">The only metadata directive present so far in the rd.xml file is:</span></span>  
  
```xml  
<Namespace Name="App.ViewModels" Browse="Required Public" Dynamic="Required Public" />  
```  
  
 <span data-ttu-id="de398-119">Вероятной причиной для сбоя является то, что в `App.Core.ViewModels.Layout.LayoutApplicationVM` не хватает метаданных, так как он находится в другом пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="de398-119">A likely candidate for the failure is that `App.Core.ViewModels.Layout.LayoutApplicationVM` is missing metadata because it's in a different namespace.</span></span>  
  
 <span data-ttu-id="de398-120">В этом случае добавления директивы среды выполнения для `App.Core.ViewModels` устранило проблему.</span><span class="sxs-lookup"><span data-stu-id="de398-120">In this case, adding a runtime directive for `App.Core.ViewModels` resolved the issue.</span></span> <span data-ttu-id="de398-121">Первопричиной был вызов API для метода <xref:System.Type.GetType%28System.String%29?displayProperty=nameWithType>, который вернул значение **NULL**, а приложение молча проигнорировало проблему до возникновения сбоя.</span><span class="sxs-lookup"><span data-stu-id="de398-121">The root cause was an API call to the <xref:System.Type.GetType%28System.String%29?displayProperty=nameWithType> method that returned **null**, and the app silently ignored the problem until a crash occurred.</span></span>  
  
 <span data-ttu-id="de398-122">В динамическом программировании хорошей практикой при использовании API отражения в [!INCLUDE[net_native](../../../includes/net-native-md.md)] считается использование перегрузок <xref:System.Type.GetType%2A?displayProperty=nameWithType>, которые создает исключение при сбое.</span><span class="sxs-lookup"><span data-stu-id="de398-122">In dynamic programming, a good practice when using reflection APIs under [!INCLUDE[net_native](../../../includes/net-native-md.md)] is to use the <xref:System.Type.GetType%2A?displayProperty=nameWithType> overloads that throw an exception on failure.</span></span>  
  
## <a name="is-this-an-isolated-case"></a><span data-ttu-id="de398-123">Это изолированный случай?</span><span class="sxs-lookup"><span data-stu-id="de398-123">Is this an isolated case?</span></span>  
 <span data-ttu-id="de398-124">Другие проблемы также могут возникнуть при использовании `App.Core.ViewModels`.</span><span class="sxs-lookup"><span data-stu-id="de398-124">Other issues might also arise when using `App.Core.ViewModels`.</span></span>  <span data-ttu-id="de398-125">Необходимо решить, стоит ли определять и устранять каждое исключение отсутствующих метаданных или лучше сэкономить время и добавить директивы для большего класса типов.</span><span class="sxs-lookup"><span data-stu-id="de398-125">You must decide whether it’s worth identifying and fixing each missing metadata exception, or saving time and adding directives for a larger class of types.</span></span>  <span data-ttu-id="de398-126">Здесь, добавление метаданных `dynamic` для `App.Core.ViewModels` может быть лучше, если результирующее увеличение размера выходного двоичного файла не проблема.</span><span class="sxs-lookup"><span data-stu-id="de398-126">Here, adding `dynamic` metadata for `App.Core.ViewModels` might be the best approach if the resulting size increase of the output binary isn’t an issue.</span></span>  
  
## <a name="could-the-code-be-rewritten"></a><span data-ttu-id="de398-127">Можно переписать код?</span><span class="sxs-lookup"><span data-stu-id="de398-127">Could the code be rewritten?</span></span>  
 <span data-ttu-id="de398-128">Если приложение использовало `typeof(LayoutApplicationVM)` вместо `Type.GetType("LayoutApplicationVM")`, то цепочка инструментов могла сохранить метаданные `browse`.</span><span class="sxs-lookup"><span data-stu-id="de398-128">If the app had used `typeof(LayoutApplicationVM)` instead of `Type.GetType("LayoutApplicationVM")`, the tool chain could have preserved `browse` metadata.</span></span>  <span data-ttu-id="de398-129">Тем не менее оно по-прежнему не создало метаданные `invoke`, которые бы привели к исключению [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md) при создании экземпляра типа.</span><span class="sxs-lookup"><span data-stu-id="de398-129">However, it still wouldn't have created `invoke` metadata, which would have led to a [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md) exception when instantiating the type.</span></span> <span data-ttu-id="de398-130">Чтобы предотвратить это исключение, как и раньше необходимо добавить директиву среды выполнения для пространства имен или тип, который задает политику `dynamic`.</span><span class="sxs-lookup"><span data-stu-id="de398-130">To prevent the exception, you'd still have to add a runtime directive for the namespace or the type that specifies the `dynamic` policy.</span></span> <span data-ttu-id="de398-131">Сведения о директивах среды выполнения см. в разделе [Справочник по конфигурационному файлу директив среды выполнения (rd.xml)](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md).</span><span class="sxs-lookup"><span data-stu-id="de398-131">For information on runtime directives, see the [Runtime Directives (rd.xml) Configuration File Reference](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de398-132">См. также</span><span class="sxs-lookup"><span data-stu-id="de398-132">See also</span></span>

- [<span data-ttu-id="de398-133">Начало работы</span><span class="sxs-lookup"><span data-stu-id="de398-133">Getting Started</span></span>](../../../docs/framework/net-native/getting-started-with-net-native.md)
- [<span data-ttu-id="de398-134">Пример: Обработка исключений при привязке данных</span><span class="sxs-lookup"><span data-stu-id="de398-134">Example: Handling Exceptions When Binding Data</span></span>](../../../docs/framework/net-native/example-handling-exceptions-when-binding-data.md)
