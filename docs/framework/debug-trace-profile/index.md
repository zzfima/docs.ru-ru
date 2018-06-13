---
title: Отладка, трассировка и профилирование
ms.date: 03/30/2017
helpviewer_keywords:
- debugging [.NET Framework]
- .NET Framework application configuration, debugging
- debugging [.NET Framework], .NET Framework application debugging
- troubleshooting applications [.NET Framework], profiling
- application development [.NET Framework], debugging
- .NET Framework application configuration, profiling
- profiling applications
- troubleshooting applications [.NET Framework], debugging
- troubleshooting applications [.NET Framework]
- application development [.NET Framework], profiling
ms.assetid: 4a04863e-2475-46f4-bc3f-3c11510c2a4b
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 481360f731297e1c287c969e6524c68e0c9c0b7e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33386474"
---
# <a name="debugging-tracing-and-profiling"></a>Отладка, трассировка и профилирование
Для отладки приложения .NET Framework компилятор и среда выполнения должны быть настроены для включения присоединения отладчика к приложению и создания символов и сопоставлений строк, если это возможно, для приложения и его соответствующего языка MSIL. После отладки управляемого приложения можно выполнить его профилирование для повышения производительности. Профилирование оценивает и описывает строки исходного кода, создающие наиболее часто выполняемый код, и время, необходимое для их выполнения.  
  
 Приложения .NET Framework можно легко отладить с помощью Visual Studio, который обрабатывает многие детали конфигурации. Если Visual Studio не установлен, вы можете проверять и улучшать производительность приложений .NET Framework с помощью классов отладки в пространстве имен <xref:System.Diagnostics> .NET Framework. Это пространство имен включает классы <xref:System.Diagnostics.Trace>, <xref:System.Diagnostics.Debug> и <xref:System.Diagnostics.TraceSource> для трассировки потока выполнения и классы <xref:System.Diagnostics.Process>, <xref:System.Diagnostics.EventLog> и <xref:System.Diagnostics.PerformanceCounter> для профилирования кода.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Включение отладки с JIT-присоединением](../../../docs/framework/debug-trace-profile/enabling-jit-attach-debugging.md)  
 Показывается, как настроить реестр для JIT-присоединения модуля отладки к приложению .NET Framework.  
  
 [Упрощение отладки образов](../../../docs/framework/debug-trace-profile/making-an-image-easier-to-debug.md)  
 Показывается, как включить отслеживание JIT и отключить оптимизацию для упрощения процесса отладки сборки.  
  
 [Трассировка и инструментирование приложений](../../../docs/framework/debug-trace-profile/tracing-and-instrumenting-applications.md)  
 Описывается, как наблюдать за приложением, пока оно выполняется, и как инструментировать его для отображения того, насколько оно хорошо работает, или того, что пошло не так.  
  
 [Диагностика ошибок посредством помощников по отладке управляемого кода](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 Сведения о помощниках по отладке управляемого кода (MDA), которые являются вспомогательными средствами отладки, работающими совместно со средой CLR для предоставления сведений о состоянии времени выполнения.  
  
 [Повышение эффективности отладки с помощью атрибутов просмотра отладчика](../../../docs/framework/debug-trace-profile/enhancing-debugging-with-the-debugger-display-attributes.md)  
 Описывается, как разработчик типа может указать, как этот тип будет выглядеть при отображении в отладчике.  
  
 [Счетчики производительности](../../../docs/framework/debug-trace-profile/performance-counters.md)  
 Описываются счетчики, которые можно использовать для отслеживания производительности приложения.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Отладка приложений ASP.NET и AJAX](http://msdn.microsoft.com/library/9d531913-541b-47b8-864d-138021fca0c6)  
 Предоставляются предварительные требования и инструкции по отладке приложения ASP.NET во время разработки или после развертывания.  
  
 [Руководство по разработке](../../../docs/framework/development-guide.md)  
 Здесь содержится руководство по всем ключевым технологическим областям и задачам для разработки приложений, включая создание, настройку, отладку, безопасность и развертывание приложений, а также сведения о динамическом программировании, взаимодействии, расширении среды, управлении памятью и работе с потоками.
