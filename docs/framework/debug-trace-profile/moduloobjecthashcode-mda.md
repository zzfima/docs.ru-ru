---
title: moduloObjectHashcode MDA
ms.date: 03/30/2017
helpviewer_keywords:
- managed debugging assistants (MDAs), hashcode modulus
- Modulo object hash code
- moduloObjectHashcode MDA
- hashcode modulus
- MDAs (managed debugging assistants), hashcode modulus
- GetHashCode method
- modulus of hashcodes
ms.assetid: b45366ff-2a7a-4b8e-ab01-537b72e9de68
ms.openlocfilehash: 65bbdfec2d7050d1b474a8186a9ea6e9bb93bd9e
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "77216180"
---
# <a name="moduloobjecthashcode-mda"></a>moduloObjectHashcode MDA
Помощник по отладке управляемого кода (MDA) `moduloObjectHashcode` изменяет поведение класса <xref:System.Object> для выполнения операции деления по модулю с хэш-кодом, возвращаемым методом <xref:System.Object.GetHashCode%2A>. Модуль по умолчанию для этого помощника по отладке управляемого кода равен 1, поэтому <xref:System.Object.GetHashCode%2A> возвращает 0 для всех объектов.  
  
## <a name="symptoms"></a>Симптомы  
 После перехода на новую версию общеязыковой среды выполнения (CLR) программа больше не работает должным образом:  
  
- Программа получает неправильный объект из <xref:System.Collections.Hashtable>.  
  
- Изменение порядка перечисления в <xref:System.Collections.Hashtable> приводит к нарушению работы программы.  
  
- Два объекта, которые ранее были равны, больше не равны.  
  
- Два объекта, которые ранее были не равны, теперь равны.  
  
## <a name="cause"></a>Причина  
 Программа может получать неверный объект из <xref:System.Collections.Hashtable> из-за реализации метода <xref:System.Object.Equals%2A> в классе для ключа в проверках на равенство для объектов <xref:System.Collections.Hashtable> путем сравнения результатов вызова со значениями, полученными в результате метода <xref:System.Object.GetHashCode%2A>. Хэш-коды не должны использоваться для проверки равенства объектов, так как два объекта могут иметь одинаковые хэш-коды, даже если соответствующие им поля имеют разные значения. Такие конфликты хэш-кодов иногда происходят, хотя и нечасто. Из-за таких конфликтов два ключа в запросе <xref:System.Collections.Hashtable>, которые не равны, кажутся равными, и <xref:System.Collections.Hashtable> возвращает неправильный объект. По соображениям производительности реализация <xref:System.Object.GetHashCode%2A> может изменяться в различных версиях среды выполнения. Поэтому конфликты, отсутствующие в одной версии, могут произойти в последующих версиях. Включите этот помощник по отладке управляемого кода, чтобы проверить, содержит ли ваш код ошибки из-за конфликтов хэш-кодов. После включения помощника метод <xref:System.Object.GetHashCode%2A> возвращает 0, что приводит к конфликту всех хэш-кодов. Единственным побочным эффектом отключения этого помощника должно быть замедление работы программы.  
  
 Порядок перечисления из <xref:System.Collections.Hashtable> может измениться между различными версиями среды выполнения, если изменяется алгоритм вычисления кэш-кодов. Чтобы проверить, зависит ли ваша программа от порядка перечисления ключей или значений в хэш-таблице, включите этот помощник по отладке управляемого кода.  
  
## <a name="resolution"></a>Решение  
 Никогда не используйте хэш-коды вместо идентификаторов объектов. Чтобы не сравнивать хэш-коды, переопределите метод <xref:System.Object.Equals%2A?displayProperty=nameWithType>.  
  
 Не следует создавать зависимости от порядка перечисления ключей или значений в хэш-таблицах.  
  
## <a name="effect-on-the-runtime"></a>Влияние на среду выполнения  
 При включении этого помощника по отладке управляемого кода программа может работать медленнее. Этот помощник просто принимает хэш-код, который был бы возвращен, и вместо него возвращает остаток от деления по модулю.  
  
## <a name="output"></a>Вывод  
 Этот помощник по отладке управляемого кода не выводит никаких данных.  
  
## <a name="configuration"></a>Конфигурация  
 Атрибут `modulus` задает модуль, используемый в хэш-коде. Значение по умолчанию ― 1.  
  
```xml  
<mdaConfig>  
  <assistants>  
    <moduloObjectHashcode modulus="1" />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>См. также:

- <xref:System.Object.GetHashCode%2A?displayProperty=nameWithType>
- <xref:System.Object.Equals%2A?displayProperty=nameWithType>
- [Диагностика ошибок посредством помощников по отладке управляемого кода](diagnosing-errors-with-managed-debugging-assistants.md)
