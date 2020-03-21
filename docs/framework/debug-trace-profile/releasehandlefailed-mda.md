---
title: releaseHandleFailed MDA
ms.date: 03/30/2017
helpviewer_keywords:
- managed debugging assistants (MDAs), handles
- release handle failed
- CriticalHandle class, run-time errors
- releaseHandleFailed MDA
- ReleaseHandle method
- SafeHandle class, run-time errors
- MDAs (managed debugging assistants), handles
ms.assetid: 44cd98ba-95e5-40a1-874d-e8e163612c51
ms.openlocfilehash: 268acb01a6777315829378e6fd8c06c46d3136d2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181751"
---
# <a name="releasehandlefailed-mda"></a>releaseHandleFailed MDA
Помощник по отладке управляемого кода (MDA) `releaseHandleFailed` активируется для уведомления разработчиков, когда метод <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A> класса, производного от <xref:System.Runtime.InteropServices.SafeHandle> или <xref:System.Runtime.InteropServices.CriticalHandle>, возвращает значение `false`.  
  
## <a name="symptoms"></a>Симптомы  
 Утечки памяти или ресурсов  Если метод <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A> класса, производного от <xref:System.Runtime.InteropServices.SafeHandle> или <xref:System.Runtime.InteropServices.CriticalHandle> завершается с ошибкой, то ресурс, инкапсулированный этим классом, может быть не освобожден или не очищен.  
  
## <a name="cause"></a>Причина  
 Пользователи должны предоставить реализацию метода <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A>, если они создают классы, производные от <xref:System.Runtime.InteropServices.SafeHandle> или <xref:System.Runtime.InteropServices.CriticalHandle>; таким образом, эти обстоятельства характерны для отдельных ресурсов. Однако действуют следующие требования.  
  
- Типы <xref:System.Runtime.InteropServices.SafeHandle> и <xref:System.Runtime.InteropServices.CriticalHandle> представляют оболочки важных ресурсов процессов. Утечка памяти может со временем сделать процесс непригодным для использования.  
  
- Метод <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A> должен работать без сбоев для выполнения своих функций. Когда процесс запрашивает такой ресурс, метод <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A> является единственным способом для его освобождения. Таким образом, ошибка подразумевает утечку ресурсов.  
  
- Все ошибки, возникающие при выполнении метода <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A> и препятствующие освобождению ресурса, представляют ошибку в реализации самого метода <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A>. Программист должен убедиться, что контракт будет выполнен, даже если этот код вызывает код, созданный другим разработчиком для выполнения своих функций.  
  
## <a name="resolution"></a>Решение  
 Код, использующий конкретный тип <xref:System.Runtime.InteropServices.SafeHandle> (или <xref:System.Runtime.InteropServices.CriticalHandle>), вызвавший уведомление MDA, следует пересмотреть, найти места, где необработанное значение дескриптора извлекается из <xref:System.Runtime.InteropServices.SafeHandle> и копируется в другом месте. Это обычная причина сбоев в реализации <xref:System.Runtime.InteropServices.SafeHandle> или <xref:System.Runtime.InteropServices.CriticalHandle>, так как использование необработанного значения дескриптора далее не отслеживается средой выполнения. Если копия необработанного дескриптора впоследствии закрывается, это может привести к сбою последующего вызова метода <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A>, поскольку попытка закрытия выполняется в том же дескрипторе, который теперь является недопустимым.  
  
 Существует несколько путей, в которых может возникнуть дублирование неверного дескриптора.  
  
- Поиск вызовов метода <xref:System.Runtime.InteropServices.SafeHandle.DangerousGetHandle%2A>. Вызовы этого метода должны быть крайне редки, и любой такой найденный вызов должны быть окружен вызовами методов <xref:System.Runtime.InteropServices.SafeHandle.DangerousAddRef%2A> и <xref:System.Runtime.InteropServices.SafeHandle.DangerousRelease%2A>. Эти последующие методы определяют участок кода, в котором можно безопасно использовать необработанное значение дескриптора. Вне этой области или в случае если число ссылок вообще никогда не увеличивается, значение дескриптора может стать недействительным в любое время путем вызова метода <xref:System.Runtime.InteropServices.SafeHandle.Dispose%2A> или <xref:System.Runtime.InteropServices.SafeHandle.Close%2A> в другом потоке. Если все случаи использования метода <xref:System.Runtime.InteropServices.SafeHandle.DangerousGetHandle%2A> отслеживаются, необходимо следовать пути, к которому прибегает необработанный дескриптор, чтобы гарантировать, что он не передан в компонент, который в конечном итоге вызывает `CloseHandle` или другой низкоуровневый собственный метод, который будет освобождать этот дескриптор.  
  
- Убедитесь, что код, который используется для инициализации <xref:System.Runtime.InteropServices.SafeHandle> с использованием допустимого необработанного значения дескриптора, владеет этим дескриптором. При создании <xref:System.Runtime.InteropServices.SafeHandle> вокруг дескриптора, который не принадлежит коду без установки параметра `ownsHandle` в значение `false` в конструкторе базового класса, и <xref:System.Runtime.InteropServices.SafeHandle>, и реальный владелец дескриптора могут пытаться закрыть этот дескриптор, что приводит к ошибке в методе <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A>, если <xref:System.Runtime.InteropServices.SafeHandle> теряет состояние гонки.  
  
- Когда <xref:System.Runtime.InteropServices.SafeHandle> маршалируется между доменами приложений, подтвердите, что используемый вывод <xref:System.Runtime.InteropServices.SafeHandle> был помечен как сериализуемый. В редких случаях, когда класс, производный от <xref:System.Runtime.InteropServices.SafeHandle>, был сделан сериализуемым, он должен реализовывать интерфейс <xref:System.Runtime.Serialization.ISerializable> или использовать один из других методов для управления процессом сериализации и десериализации вручную. Это необходимо, поскольку действие сериализации по умолчанию заключается в создании побитового клона включенного необработанного значения дескриптора, в результате чего два экземпляра <xref:System.Runtime.InteropServices.SafeHandle> думают, что они владеют одним и тем же дескриптором. Оба будут пытаться вызвать метод <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A> в том же дескрипторе в определенный момент. Второму <xref:System.Runtime.InteropServices.SafeHandle> это сделать не удастся. Правильный способ действий при сериализации <xref:System.Runtime.InteropServices.SafeHandle> заключается в вызове функции `DuplicateHandle` или аналогичной функции для вашего собственного типа дескриптора, чтобы создать другую копию действительного дескриптора. Если ваш тип дескриптора не поддерживает такое действие, то обертывающий его тип <xref:System.Runtime.InteropServices.SafeHandle> нельзя сделать сериализуемым.  
  
- Можно отслеживать, где дескриптор закрывается раньше, что приводит к возникновению ошибки при последнем вызове метода <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A>, установив точку останова отладчика в исходной программе, используемой для освобождения дескриптора, например в функции `CloseHandle`. Это может оказаться невозможным в сценариях нагрузочных тестов или даже в функциональных тестах среднего размера из-за большого объема трафика, с которым часто сталкиваются подобные программы. Может помочь инструментирование кода, который вызывает собственный метод освобождения, чтобы записывать удостоверение вызывающего объекта или возможно полную трассировку стека и значение дескриптора.  Значение дескриптора можно сравнивать со значением, предоставленным MDA.  
  
- Обратите внимание, что некоторые типы собственных дескрипторов, например все дескрипторы Win32, которые могут быть освобождены с помощью функции `CloseHandle`, совместно используют одно пространство имен дескрипторов. Ошибочное освобождение одного типа дескриптора может вызвать проблемы с другим. Например, случайное закрытие дескриптора события Win32 дважды может привести к вероятному преждевременному закрытию несвязанного дескриптора файла. Это происходит, когда дескриптор освобождается и значение дескриптора становится доступным для использования в целях отслеживания другого ресурса, возможно другого типа. Если это происходит и приводит к ошибочному повторному освобождению, дескриптор несвязанного потока может стать недействительным.  
  
## <a name="effect-on-the-runtime"></a>Влияние на среду выполнения  
 Этот помощник отладки управляемого кода не оказывает никакого влияния на среду CLR.  
  
## <a name="output"></a>Выходные данные  
 Сообщение, указывающее, что <xref:System.Runtime.InteropServices.SafeHandle> или <xref:System.Runtime.InteropServices.CriticalHandle> не удалось должным образом освободить дескриптор. Пример:  
  
```output
"A SafeHandle or CriticalHandle of type 'MyBrokenSafeHandle'
failed to properly release the handle with value 0x0000BEEF. This
usually indicates that the handle was released incorrectly via
another means (such as extracting the handle using DangerousGetHandle
and closing it directly or building another SafeHandle around it."  
```  
  
## <a name="configuration"></a>Конфигурация  
  
```xml  
<mdaConfig>  
  <assistants>  
    <releaseHandleFailed/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a>Пример  
 Ниже приведен пример кода, который может активировать MDA `releaseHandleFailed`.  
  
```csharp
bool ReleaseHandle()  
{  
    // Calling the Win32 CloseHandle function to release the
    // native handle wrapped by this SafeHandle. This method returns
    // false on failure, but should only fail if the input is invalid
    // (which should not happen here). The method specifically must not
    // fail simply because of lack of resources or other transient
    // failures beyond the user’s control. That would make it unacceptable
    // to call CloseHandle as part of the implementation of this method.  
    return CloseHandle(handle);  
}  
```  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [Диагностика ошибок посредством помощников по отладке управляемого кода](diagnosing-errors-with-managed-debugging-assistants.md)
- [Маршалинг взаимодействия](../interop/interop-marshaling.md)
