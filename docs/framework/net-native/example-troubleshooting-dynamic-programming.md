---
title: 'Пример: Устранение неполадок динамического программирования'
ms.date: 03/30/2017
ms.assetid: 42ed860a-a022-4682-8b7f-7c9870784671
ms.openlocfilehash: ff179854066d024a89cb5a84a19d0b9bb054d6e5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128443"
---
# <a name="example-troubleshooting-dynamic-programming"></a>Пример: Устранение неполадок динамического программирования
> [!NOTE]
> В этом разделе рассматривается предварительная версия программного обеспечения для разработчиков машинного кода .NET. Предварительную версию можно скачать на [веб-сайте Microsoft Connect](https://go.microsoft.com/fwlink/?LinkId=394611) (требуется регистрация).  
  
 Не все ошибки поиска метаданных в приложениях, разработанных с помощью цепочки средств .NET Native, приводят к возникновению исключения.  Некоторые могут проявляться в непредсказуемом виде в приложении.  В следующем примере показано нарушение доступа, вызванное ссылкой на пустой объект:  
  
```output
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
  
 Давайте попробуем устранить данное исключение, используя трехшаговый подход, описанный в подразделе "Устранение вручную проблем с отсутствующими метаданными" раздела [Начало работы](getting-started-with-net-native.md).  
  
## <a name="what-was-the-app-doing"></a>Что делало это приложение?  
 В первую очередь следует отметить механизм обработки ключевого слова `async` в начале стека.  Определить, что приложение действительно делало в методе `async` может быть проблематично, так как стек потерял контекст исходного вызова и выполнял код `async` в другом потоке. Тем не менее, мы можем предположить, что приложение пытается загрузить свою первую страницу.  В реализации для `NavigationArgs.Setup` нарушение доступа было вызвано следующим кодом:  
  
`AppViewModel.Current.LayoutVM.PageMap`  
  
 В этом случае свойство `LayoutVM` для `AppViewModel.Current` имело значение **NULL**.  Отсутствие некоторых метаданных вызвало небольшую разницу в поведении и привело к инициализации свойства вместо набора, как ожидало приложение.  Задание точки останова в коде, в котором должно было быть реализовано `LayoutVM`, может пролить свет на ситуацию.  Тем не менее, обратите внимание, что типом `LayoutVM` является `App.Core.ViewModels.Layout.LayoutApplicationVM`.  Единственной директивой метаданных, присутствующей в файле rd.xml на настоящий момент, является:  
  
```xml  
<Namespace Name="App.ViewModels" Browse="Required Public" Dynamic="Required Public" />  
```  
  
 Вероятной причиной для сбоя является то, что в `App.Core.ViewModels.Layout.LayoutApplicationVM` не хватает метаданных, так как он находится в другом пространстве имен.  
  
 В этом случае добавления директивы среды выполнения для `App.Core.ViewModels` устранило проблему. Первопричиной был вызов API для метода <xref:System.Type.GetType%28System.String%29?displayProperty=nameWithType>, который вернул значение **NULL**, а приложение молча проигнорировало проблему до возникновения сбоя.  
  
 В динамическом программировании при использовании API отражения в .NET Native рекомендуется использовать перегрузки <xref:System.Type.GetType%2A?displayProperty=nameWithType>, которые вызывают исключение при сбое.  
  
## <a name="is-this-an-isolated-case"></a>Это изолированный случай?  
 Другие проблемы также могут возникнуть при использовании `App.Core.ViewModels`.  Необходимо решить, стоит ли определять и устранять каждое исключение отсутствующих метаданных или лучше сэкономить время и добавить директивы для большего класса типов.  Здесь, добавление метаданных `dynamic` для `App.Core.ViewModels` может быть лучше, если результирующее увеличение размера выходного двоичного файла не проблема.  
  
## <a name="could-the-code-be-rewritten"></a>Можно переписать код?  
 Если приложение использовало `typeof(LayoutApplicationVM)` вместо `Type.GetType("LayoutApplicationVM")`, то цепочка инструментов могла сохранить метаданные `browse`.  Тем не менее оно по-прежнему не создало метаданные `invoke`, которые бы привели к исключению [MissingMetadataException](missingmetadataexception-class-net-native.md) при создании экземпляра типа. Чтобы предотвратить это исключение, как и раньше необходимо добавить директиву среды выполнения для пространства имен или тип, который задает политику `dynamic`. Сведения о директивах среды выполнения см. в разделе [Справочник по конфигурационному файлу директив среды выполнения (rd.xml)](runtime-directives-rd-xml-configuration-file-reference.md).  
  
## <a name="see-also"></a>См. также

- [Начало работы](getting-started-with-net-native.md)
- [Пример. Обработка исключений при привязке данных](example-handling-exceptions-when-binding-data.md)
