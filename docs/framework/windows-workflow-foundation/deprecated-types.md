---
title: Устаревшие типы в Windows Workflow Foundation
ms.date: 03/30/2017
ms.assetid: 4aebe928-a964-4c1c-abf7-0dbbd3604b13
ms.openlocfilehash: 899d21f23c0500a1df01916d1da210b2f9bea95b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33512431"
---
# <a name="deprecated-types-in-windows-workflow-foundation"></a>Устаревшие типы в Windows Workflow Foundation
В .NET 4 группа разработки по рабочим процессам представила полностью новую подсистему рабочих процессов в пространстве имен <xref:System.Activities>. С выпуском бета-версии .NET 4.5 Мы отмечаем большинство типов в «WF 3» <xref:System.Workflow.Activities>, <xref:System.Workflow.ComponentModel>, и <xref:System.Workflow.Runtime> пространства имен, как устаревшие.  
  
## <a name="obsolete-namespaces-and-tools"></a>Устаревшие пространства имен и средства  
 Следующие сборки содержат один и более открытых типов, которые станут устаревшими.  
  
-   System.Workflow.Activities.dll  
  
-   System.Workflow.ComponentModel.dll  
  
-   System.Workflow.Runtime.dll  
  
-   System.WorkflowServices.dll  
  
-   Microsoft.Workflow.DebugController.dll  
  
-   Microsoft.Workflow.Compiler.exe  
  
-   Wfc.exe  
  
 В результате этого клиенты, использующие устаревшие API WF 3, увидят предупреждения при сборке с сообщением следующего вида:  
  
 **Предупреждение BC40000: X устарело: типы WF 3 устарели. Вместо нее используйте WF 4.** В одном из последующих выпусков (не в 4.5) типы будут удалены из .NET Framework, но временной промежуток до этого еще не определен. Текущий шаг позволяет донести наши планы до клиентов и дает им достаточно времени для перехода на новую модель WF4. Мы Конечно, продолжит поддерживает эти типы WF 3 в разделе [политики жизненного цикла поддержки Microsoft](http://aka.ms/MicrosoftSupportLifecycle). Существующие приложения WF3 будут запускаться в .NET 4.5 без проблем; [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] будет поддерживать новые и существующие решения на основе WF3.  
  
 Основанные на правилах типы в пространстве имен <xref:System.Workflow.Activities.Rules>, не имеющие замены в WF 4.5, не устарели.  
  
 Клиенты, которые планируют перенести свои приложения в WF 4 будет поиск справки в [руководство по миграции рабочего процесса 4](migration-guidance.md).
