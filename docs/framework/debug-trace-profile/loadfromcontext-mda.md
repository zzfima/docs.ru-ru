---
title: Помощник по отладке управляемого кода loadFromContext
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), LoadFrom context
- managed debugging assistants (MDAs), LoadFrom context
- LoadFrom context
- LoadFromContext MDA
ms.assetid: a9b14db1-d3a9-4150-a767-dcf3aea0071a
ms.openlocfilehash: d0090a0272d1c3b6175b351175689df1e1e4fdbd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181806"
---
# <a name="loadfromcontext-mda"></a>Помощник по отладке управляемого кода loadFromContext
Помощник по отладке управляемого кода (MDA) `loadFromContext` активируется при загрузке сборки в контекст `LoadFrom`. Эта ситуация может возникнуть в результате вызова метода <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> или других аналогичных методов.  
  
## <a name="symptoms"></a>Симптомы  
 Использование некоторых методов загрузчика может привести к загрузке сборок в контекст `LoadFrom`. Использование этого контекста может привести к неожиданному поведению при сериализации, приведении типов и разрешении зависимостей. Чтобы избежать этих проблем, рекомендуется загружать сборки в контекст `Load`. Без этого помощника по отладке управляемого кода определить, в какой контекст загружена сборка, трудно.  
  
## <a name="cause"></a>Причина  
 Как правило, при использовании пути за пределами контекста `Load`, например глобального кэша сборок или свойства <xref:System.AppDomainSetup.ApplicationBase%2A?displayProperty=nameWithType>, сборка загружается в контекст `LoadFrom`.  
  
## <a name="resolution"></a>Решение  
 Настройте приложения таким образом, чтобы вызовы <xref:System.Reflection.Assembly.LoadFrom%2A> больше не требовались. Это можно сделать следующими способами:  
  
- Установите сборки в глобальный кэш сборок.  
  
- Поместите сборки в каталог <xref:System.AppDomainSetup.ApplicationBase%2A> для <xref:System.AppDomain>. Для домена по умолчанию каталог <xref:System.AppDomainSetup.ApplicationBase%2A> содержит исполняемый файл, который запустил процесс. Если перемещать сборку неудобно, также может потребоваться создать новый <xref:System.AppDomain>.  
  
- Если зависимые сборки находятся в дочерних папках по отношению к исполняемому файлу, добавьте путь проверки в файл конфигурации приложения (.config) или во вторичные домены приложения.  
  
 В каждом случае можно изменить код, включив в него метод <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>.  
  
## <a name="effect-on-the-runtime"></a>Влияние на среду выполнения  
 Помощник по отладке управляемого кода не оказывает никакого воздействия на общеязыковую среду выполнения (CLR). В качестве результата запроса на загрузку он возвращает используемый контекст.  
  
## <a name="output"></a>Выходные данные  
 Помощник по отладке управляемого кода сообщает, что сборка была загружена в контекст `LoadFrom`. В выводе указаны простое имя сборки и путь к ней. В выводе также указаны рекомендации, позволяющие избежать использования контекста `LoadFrom`.  
  
## <a name="configuration"></a>Конфигурация  
  
```xml  
<mdaConfig>  
  <assistants>  
    <loadFromContext />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a>Пример  
 В следующем примере кода показана ситуация, которая может привести к запуску помощника по отладке управляемого кода:  
  
```csharp
using System.Reflection;  
namespace ConsoleApplication1  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            // The following call caused the LoadFrom context to be used  
            // because the assembly is loaded using LoadFrom and the path is
            // located outside of the Load context probing path.
            Assembly.LoadFrom(@"C:\Text\Test.dll");  
        }  
    }  
}  
```  
  
## <a name="see-also"></a>См. также раздел

- [Диагностика ошибок посредством помощников по отладке управляемого кода](diagnosing-errors-with-managed-debugging-assistants.md)
