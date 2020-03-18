---
title: Определение, когда следует реализовать асинхронную модель, основанную на событиях
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- Event-based Asynchronous Pattern
- ProgressChangedEventArgs class
- BackgroundWorker component
- events [.NET Framework], asynchronous
- AsyncOperationManager class
- threading [.NET Framework], asynchronous features
- AsyncOperation class
- AsyncCompletedEventArgs class
ms.assetid: a00046aa-785d-4f7f-a8e5-d06475ea50da
ms.openlocfilehash: 5fca32953af91184fe99d8ef6afe5a2374f325d6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "67663719"
---
# <a name="deciding-when-to-implement-the-event-based-asynchronous-pattern"></a>Определение, когда следует реализовать асинхронную модель, основанную на событиях

Асинхронная модель на основе событий применяется для предоставления асинхронного поведения класса. С момента ее появления .NET Framework определяет две модели для предоставления асинхронного поведения: на основе интерфейса <xref:System.IAsyncResult?displayProperty=nameWithType> и на основе событий. Эта статья описывает ситуации, в которых вам следует применять ту или иную модель.

Дополнительные сведения об асинхронном программировании для интерфейса <xref:System.IAsyncResult> вы найдете в статье об [асинхронной модели программирования (APM)](../../../docs/standard/asynchronous-programming-patterns/asynchronous-programming-model-apm.md).

## <a name="general-principles"></a>Общие принципы

Обычно для всех асинхронных функций лучше применять асинхронную модель на основе событий. Но есть несколько требований, которым она не полностью соответствует. Если они применимы в вашей ситуации, в дополнение к модели на основе событий следует реализовать модель <xref:System.IAsyncResult>.

> [!NOTE]
> Модель <xref:System.IAsyncResult> очень редко реализуется отдельно, без модели на основе событий.

## <a name="guidelines"></a>Рекомендации

Ниже перечислены рекомендации по выбору асинхронной модели на основе событий.

- Используйте модель на основе событий в качестве основного API для асинхронных возможностей класса.

- Не предоставляйте модель <xref:System.IAsyncResult>, если класс используется в основном в клиентском приложении, например Windows Forms.

- Предоставляйте модель <xref:System.IAsyncResult> только в тех случаях, когда это необходимо для конкретных требований. Например, модель <xref:System.IAsyncResult> может потребоваться для совместимости с уже существующими API.

- Не предоставляйте модель <xref:System.IAsyncResult> отдельно, без модели на основе событий.

- Если потребуется модель <xref:System.IAsyncResult>, предоставляйте ее только в качестве дополнительной возможности. Например, если вы создаете прокси-объект, создайте модель на основе событий в качестве стандартного варианта, а модель <xref:System.IAsyncResult> предоставляйте опционально.

- Модели на основе событий следует основывать на вашей реализации модели <xref:System.IAsyncResult>.

- По возможности не размещайте модель на основе событий и модель <xref:System.IAsyncResult> в одном классе. Модель на основе событий должна размещаться в классах "более высокого уровня" относительно модели <xref:System.IAsyncResult>. Сравните, например, модель на основе событий для компонента <xref:System.Net.WebClient> с моделью <xref:System.IAsyncResult> в классе <xref:System.Web.HttpRequest>.

  - Используйте один и тот же класс для предоставления модели на основе событий и модели <xref:System.IAsyncResult> только в том случае, если это необходимо для совместимости. Например, если вы уже опубликовали API, в котором реализована модель <xref:System.IAsyncResult>, ее придется сохранить для обеспечения обратной совместимости<xref:System.IAsyncResult>.

  - Также допустимо размещать модель на основе событий и модель <xref:System.IAsyncResult> в одном классе в тех случаях, когда сложность объектной модели перевешивает преимущества от раздельной реализации. Гораздо лучше предоставить обе модели в одном классе, чем вовсе не предоставлять модель на основе событий.

  - Если вам придется разместить модель на основе событий в том же классе, что и модель <xref:System.IAsyncResult>, используйте <xref:System.ComponentModel.EditorBrowsableAttribute> со значением <xref:System.ComponentModel.EditorBrowsableState.Advanced>, чтобы обозначить реализацию модели <xref:System.IAsyncResult> как дополнительную функцию. В этом случае среды разработки, например Visual Studio IntelliSense, не будут отображать свойства и методы <xref:System.IAsyncResult>. Эти свойства и методы будут функционировать как прежде, но не будут захламлять рабочее пространство API-интерфейса для разработчика, работающего в IntelliSense.

## <a name="criteria-for-exposing-the-iasyncresult-pattern-in-addition-to-the-event-based-pattern"></a>Критерии для предоставления модели IAsyncResult в дополнение к модели на основе событий

В описанных выше сценариях асинхронная модель на основе событий дает целый ряд преимуществ, но имеет и некоторые недостатки. Их важно учитывать, если у вас высокие требования к производительности.

Есть три сценария, для которых модель на основе событий подходит хуже, чем модель <xref:System.IAsyncResult>:

- ожидание с блокировкой для одного <xref:System.IAsyncResult>;

- ожидание с блокировкой для нескольких объектов <xref:System.IAsyncResult>;

- опрос завершения для <xref:System.IAsyncResult>.

Все эти сценарии можно реализовать с помощью модели на основе событий, но такое решение будет более громоздким, чем использование модели <xref:System.IAsyncResult>.

Разработчики часто используют модель <xref:System.IAsyncResult> для служб с высокими требованиями к производительности. Например, сценарий с опросом завершения является одним из методов повышения производительности сервера.

Эффективность модели на основе событий ниже, чем у модели <xref:System.IAsyncResult>, поскольку она создает несколько объектов (особенно <xref:System.EventArgs>) и синхронизируется между потоками.

Следующий список содержит рекомендации на случай, если вы решили использовать модель <xref:System.IAsyncResult>.

- Предоставляйте модель <xref:System.IAsyncResult> только в том случае, когда строго необходима поддержка объектов <xref:System.Threading.WaitHandle> или <xref:System.IAsyncResult>.

- Предоставляйте модель <xref:System.IAsyncResult> только в том случае, если у вас уже есть API, который использует модель <xref:System.IAsyncResult>.

- Если у вас есть существующий API, основанный на модели <xref:System.IAsyncResult>, постарайтесь в следующем выпуске реализовать и модель на основе событий.

- Предоставляйте модель <xref:System.IAsyncResult> только в том случае, если у вас высокие требования к производительности, которые гарантированно недостижимы при применении модели на основе событий, но могут быть достижимы с помощью модели <xref:System.IAsyncResult>.

## <a name="see-also"></a>См. также раздел

- [Практическое руководство. Реализация компонента, поддерживающего асинхронную модель на основе событий](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md)
- [Асинхронная модель на основе событий (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)
- [Реализация асинхронной модели, основанной на событиях](../../../docs/standard/asynchronous-programming-patterns/implementing-the-event-based-asynchronous-pattern.md)
- [Рекомендации по реализации асинхронной модели, основанной на событиях](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md)
- [Обзор асинхронной модели, основанной на событиях](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
