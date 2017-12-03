---
title: "Как отображать ошибки проверок в повторно размещенном конструкторе"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5aa8fb53-8f75-433b-bc06-7c7d33583d5d
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b9f76f1ad5282ecf10a3ce58db0f6e1bd8df1b4d
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-display-validation-errors-in-a-rehosted-designer"></a>Как отображать ошибки проверок в повторно размещенном конструкторе
В этом разделе описывается получение и публикация ошибок проверки в повторно размещенном экземпляре средства [!INCLUDE[wfd1](../../../includes/wfd1-md.md)]. Это предоставляет процедуру подтверждения того, что рабочий процесс в повторно размещенном конструкторе является допустимым.  
  
 Эта задача имеет две части. Первой задачей является предоставление реализации <xref:System.Activities.Presentation.Validation.IValidationErrorService>.  Имеется один очень важный метод, реализуемый в этом интерфейсе, <xref:System.Activities.Presentation.Validation.IValidationErrorService.ShowValidationErrors%2A>, который передает список объектов <xref:System.Activities.Presentation.Validation.ValidationErrorInfo>, содержащих сведения об ошибках, в журнал отладки.  После реализации интерфейса сведения об ошибках получаются путем публикации экземпляра этой реализации в контексте редактирования.  
  
### <a name="implement-the-ivalidationerrorservice-interface"></a>Реализация интерфейса IValidationErrorService  
  
1.  Здесь приводится образец кода для простой реализации, которая записывает ошибки проверки в журнал отладки.  
  
    ```  
    using System.Activities.Presentation.Validation;  
    using System.Collections.Generic;  
    using System.Diagnostics;  
    using System.Linq;  
  
    namespace VariableFinderShell  
    {  
        class DebugValidationErrorService : IValidationErrorService  
        {  
            public void ShowValidationErrors(IList<ValidationErrorInfo> errors)  
            {  
                errors.ToList().ForEach(vei => Debug.WriteLine(string.Format("Error: {0} ", vei.Message)));  
            }  
        }  
    }  
    ```  
  
### <a name="publishing-to-the-editing-context"></a>Публикация в контексте редактирования  
  
1.  Здесь приводится код, который публикует это в контексте редактирования.  
  
    ```  
    wd.Context.Services.Publish<IValidationErrorService>(new DebugValidationErrorService());  
    ```
