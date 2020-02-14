---
title: Помощник по отладке управляемого кода invalidApartmentStateChange
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), invalid apartment state
- managed debugging assistants (MDAs), invalid apartment state
- InvalidApartmentStateChange MDA
- invalid apartment state changes
- threading [.NET Framework], apartment states
- apartment states
- threading [.NET Framework], managed debugging assistants
- COM apartment states
ms.assetid: e56fb9df-5286-4be7-b313-540c4d876cd7
ms.openlocfilehash: 8acafcc2fba9a7d30cc77f25f06adaca7c79db32
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "77217416"
---
# <a name="invalidapartmentstatechange-mda"></a>Помощник по отладке управляемого кода invalidApartmentStateChange
Помощник по отладке управляемого кода (MDA) `invalidApartmentStateChange` активируется при возникновении одной из двух следующих проблем.  
  
- Предпринята попытка изменить состояние подразделения COM потока, который уже был инициализирован COM в другом состоянии подразделения.  
  
- Неожиданное изменение состояния подразделения COM потока.  
  
## <a name="symptoms"></a>Симптомы  
  
- Состояние подразделения COM отличается от запрошенного. Это может привести к использованию прокси-серверов для COM-компонентов, имеющих потоковую модель, отличную от текущей. Это, в свою очередь, может привести к возникновению исключения <xref:System.InvalidCastException> при вызове COM-объекта через интерфейсы, которые не настроены для маршалинга между подразделениями.  
  
- Состояние подразделения COM потока отличается от ожидаемого. Это может привести к <xref:System.Runtime.InteropServices.COMException> с HRESULT RPC_E_WRONG_THREAD, а также <xref:System.InvalidCastException> при вызовах [вызываемой оболочки времени выполнения](../../standard/native-interop/runtime-callable-wrapper.md) (RCW). Кроме того, сразу несколько потоков могут одновременно осуществлять доступ к некоторым однопоточным COM-компонентам, что может привести к повреждению или потере данных.  
  
## <a name="cause"></a>Причина  
  
- Поток ранее был инициализирован в другом состоянии подразделения СОМ. Обратите внимание, что состояние потока подразделения может быть задано явным или неявным образом. Явные операции содержат свойство <xref:System.Threading.Thread.ApartmentState%2A?displayProperty=nameWithType> и методы <xref:System.Threading.Thread.SetApartmentState%2A> и <xref:System.Threading.Thread.TrySetApartmentState%2A>. Поток, созданный с помощью метода <xref:System.Threading.Thread.Start%2A>, неявно задан как <xref:System.Threading.ApartmentState.MTA> до тех пор, пока <xref:System.Threading.Thread.SetApartmentState%2A> не будет вызван до запуска потока. Основной поток приложения также неявно инициализирован как <xref:System.Threading.ApartmentState.MTA> до тех пор, пока в основном методе не будет указан атрибут <xref:System.STAThreadAttribute>.  
  
- В потоке вызван метод `CoUninitialize` (или метод `CoInitializeEx`) с другой моделью параллелизма.  
  
## <a name="resolution"></a>Решение  
 Задайте состояние подразделения потока перед началом его выполнения либо примените атрибут <xref:System.STAThreadAttribute> или <xref:System.MTAThreadAttribute> атрибут к основному методу приложения.  
  
 Во втором случае в идеале код, вызывающий метод `CoUninitialize`, следует изменить для задержки вызова до тех пор, пока поток не будет завершен и не перестанет использовать RCW и базовые СОМ-компоненты. Однако если не удается изменить код, который вызывает метод`CoUninitialize`, то нельзя использовать RCW из потоков, для которых выполнена отмена инициализации.  
  
## <a name="effect-on-the-runtime"></a>Влияние на среду выполнения  
 Этот помощник отладки управляемого кода не оказывает никакого влияния на среду CLR.  
  
## <a name="output"></a>Вывод  
 Состояние контейнера СОМ текущего потока и состояние, которое пытался применить код.  
  
## <a name="configuration"></a>Конфигурация  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidApartmentStateChange />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a>Пример  
 Следующий пример кода демонстрирует ситуацию, которая может активировать данный MDA.  
  
```csharp
using System.Threading;  
namespace ApartmentStateMDA  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            Thread.CurrentThread.SetApartmentState(ApartmentState.STA);  
        }  
    }  
}  
```  
  
## <a name="see-also"></a>См. также:

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [Диагностика ошибок посредством помощников по отладке управляемого кода](diagnosing-errors-with-managed-debugging-assistants.md)
- [Маршалинг взаимодействия](../interop/interop-marshaling.md)
