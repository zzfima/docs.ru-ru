---
title: Настройка проверки действий
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 25a4eccb-b8fc-4857-a01d-2683b6341219
caps.latest.revision: 5
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f0b7099cbae2faf53e99f73a52f4c25f42ed6834
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2018
---
# <a name="configuring-activity-validation"></a>Настройка проверки действий
Проверка действия позволяет авторам и пользователям действий выявлять ошибки и сообщать о них в конфигурации любого действия до его выполнения. Windows Workflow Foundation (WF) предоставляет следующие три способа проверки действий.  
  
-   Атрибуты `RequiredArgument` и `OverloadGroup`.  
  
-   Императивная, основанная на коде проверка.  
  
-   Декларативные ограничения.  
  
 Атрибуты `RequiredArgument` и `OverloadGroup` указывают, что определенные аргументы в действии являются обязательными. Императивная, основанная на коде проверка предоставляет действию простой способ выполнения самопроверки, а декларативные ограничения позволяют выполнять проверку действия и его связи с рабочим процессом, содержащим это действие. Если действие не настроено в соответствии с требованиями проверки, то возвращаются ошибки проверки и предупреждения. Если рабочий процесс, содержащий действие, создан с использованием конструктора рабочих процессов, то все ошибки проверки и предупреждения отображаются в этом конструкторе. Если рабочий процесс создан за пределами конструктора рабочих процессов, то все ошибки проверки возвращаются при вызове рабочего процесса. Независимо от способа создания рабочего процесса, рабочий процесс, содержащий ошибки проверки, выполнен не будет. В этом разделе представлены общие сведения об этих типах проверки действий и способах ее вызова.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Обязательные аргументы и группы перегрузки](../../../docs/framework/windows-workflow-foundation/required-arguments-and-overload-groups.md)  
 Описывает процесс использования атрибутов `RequiredArgument` и `OverloadGroup` для выполнения проверки.  
  
 [Проверка на основе императивного кода](../../../docs/framework/windows-workflow-foundation/imperative-code-based-validation.md)  
 Описывает процесс использования проверки на уровне коде для действий, основанных на <xref:System.Activities.CodeActivity> и <xref:System.Activities.NativeActivity>.  
  
 [Декларативные ограничения](../../../docs/framework/windows-workflow-foundation/declarative-constraints.md)  
 Описывает процесс использования декларативных ограничений для выполнения проверки сложных действий.  
  
 [Вызов проверки действия](../../../docs/framework/windows-workflow-foundation/invoking-activity-validation.md)  
 Описывает процесс автоматического вызова проверки действия и способы явного вызова проверки.  
  
## <a name="reference"></a>Ссылка  
  
## <a name="related-sections"></a>Связанные разделы
