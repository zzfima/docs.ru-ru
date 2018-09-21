---
title: Параметры разработки действий в WF
ms.date: 03/30/2017
ms.assetid: b9061f5f-12c3-47f0-adbe-1330e2714c94
ms.openlocfilehash: 219d759cd1390a83abfb90af509b21047085f6e9
ms.sourcegitcommit: 2350a091ef6459f0fcfd894301242400374d8558
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/21/2018
ms.locfileid: "46529597"
---
# <a name="activity-authoring-options-in-wf"></a>Параметры разработки действий в WF
[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] обеспечивает несколько вариантов разработки настраиваемых действий. Выбор правильного метода создания определенного действия зависит от требований функций времени выполнения.  
  
## <a name="deciding-which-base-activity-class-to-use-for-authoring-custom-activities"></a>Выбор базового класса действий для разработки настраиваемых действий  
 В следующей таблице перечислены функции, доступные в базовых классах настраиваемых действий.  
  
|Базовый класс действия|Доступные функции|  
|-------------------------|------------------------|  
|<xref:System.Activities.Activity>|Формирует составное действие из групп системных и настраиваемых действий.|  
|<xref:System.Activities.CodeActivity>|Реализует императивные функции путем предоставления метода <xref:System.Activities.CodeActivity%601.Execute%2A>, который можно переопределить. Также обеспечивает доступ к отслеживанию, переменным и аргументам.|  
|<xref:System.Activities.NativeActivity>|Обеспечивает все функции <xref:System.Activities.CodeActivity>, а также прерывание выполнения действий, отмену выполнения дочерних действий, использование закладок, а также планирование действий, задач действий и функций.|  
|<xref:System.Activities.DynamicActivity>|Обеспечивает подход, схожий с DOM, к действиям построения, при которых используется конструктор WF и механизмы среды выполнения с <xref:System.ComponentModel.ICustomTypeDescriptor>, что обеспечивает возможность создания новых действий без определения новых типов.|  
  
## <a name="authoring-activities-using-activity"></a>Разработка действий с помощью действия  
 Действия, которые являются производными от <xref:System.Activities.Activity>, реализуют функциональность путем сборки других существующих действий. Такими действиями могут быть существующие настраиваемые действия и действия из библиотеки действий [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)]. Сборка этих действий является наиболее простым способом создания пользовательских функциональных возможностей. Этот подход обычно используется при создании рабочих процессов в среде виртуальной разработки.  
  
## <a name="authoring-activities-using-codeactivity-or-asynccodeactivity"></a>Разработка действий с помощью CodeActivity или AsyncCodeActivity  
 Действия, которые являются производными от <xref:System.Activities.CodeActivity> или <xref:System.Activities.AsyncCodeActivity>, могут реализовывать императивные функции путем переопределения метода <xref:System.Activities.CodeActivity%601.Execute%2A> с помощью настраиваемого императивного кода. Настраиваемый код выполняется при выполнении действия средой выполнения. Действия, созданные таким образом, имеют доступ к пользовательским функциям, но не ко всем функциям среды выполнения, таким как полный доступ к среде выполнения, возможность планировать дочерние действия, создание закладок и поддержка методов Cancel или Abort. При своем выполнении <xref:System.Activities.CodeActivity> получает доступ к сокращенной версии среды выполнения (посредством класса <xref:System.Activities.CodeActivityContext> или <xref:System.Activities.AsyncCodeActivityContext>). Действия, созданные с помощью <xref:System.Activities.CodeActivity>, имеют доступ к разрешению аргументов и переменных, расширениям и отслеживанию. Асинхронное планирование действий можно выполнить с помощью <xref:System.Activities.AsyncCodeActivity>.  
  
## <a name="authoring-activities-using-nativeactivity"></a>Разработка действий с помощью NativeActivity  
 Действия, которые являются производными от <xref:System.Activities.NativeActivity> аналогично производным действиям от <xref:System.Activities.CodeActivity>, создают императивные функции путем переопределения <xref:System.Activities.NativeActivity.Execute%2A>, но также имеют доступ ко всем функциям среды выполнения рабочего процесса благодаря <xref:System.Activities.NativeActivityContext>, который передается методу <xref:System.Activities.NativeActivity.Execute%2A>. Этот контекст поддерживает планирование и отмену дочерних действий, выполнение объектов <xref:System.Activities.ActivityAction> и <xref:System.Activities.ActivityFunc%601>, потоки транзакций в рабочем процессе, вызов асинхронных процессов, отмену и прерывание выполнения, доступ к свойствам выполнения и расширениям, а также закладки (маркеры для возобновления приостановленных рабочих процессов).  
  
## <a name="authoring-activities-using-dynamicactivity"></a>Разработка действий с помощью DynamicActivity  
 В отличие от трех других типов действий новая функциональность создается не путем создания новых типов из <xref:System.Activities.DynamicActivity> (этот класс является запечатанным), а путем сборки функциональности в свойства <xref:System.Activities.DynamicActivity.Properties%2A> и <xref:System.Activities.DynamicActivity.Implementation%2A> с помощью модели DOM действий.  
  
## <a name="authoring-activities-that-return-a-result"></a>Разработка действий, возвращающих результат  
 Многие действия должны возвращать результат после выполнения. Хотя для этих целей всегда можно определить настраиваемый <xref:System.Activities.OutArgument%601> для действия, рекомендуется вместо этого использовать <xref:System.Activities.Activity%601> или сформировать из <xref:System.Activities.CodeActivity%601> или <xref:System.Activities.NativeActivity%601>. Все эти базовые классы имеют аргумент <xref:System.Activities.OutArgument%601> с именем Result, который действие может использовать для возвращаемого значения. Действия, возвращающие результат, должны использоваться, только если требуется возвратить из действия лишь один результат. Если требуется возвратить несколько результатов, следует использовать отдельные члены <xref:System.Activities.OutArgument%601>.
