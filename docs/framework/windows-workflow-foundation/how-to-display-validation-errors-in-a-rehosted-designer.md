---
title: "Как отображать ошибки проверок в повторно размещенном конструкторе | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5aa8fb53-8f75-433b-bc06-7c7d33583d5d
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# Как отображать ошибки проверок в повторно размещенном конструкторе
В этом разделе описывается получение и публикация ошибок проверки в повторно размещенном экземпляре средства [!INCLUDE[wfd1](../../../includes/wfd1-md.md)].Это предоставляет процедуру подтверждения того, что рабочий процесс в повторно размещенном конструкторе является допустимым.  
  
 Эта задача имеет две части.Первой задачей является предоставление реализации <xref:System.Activities.Presentation.Validation.IValidationErrorService>.Имеется один очень важный метод, реализуемый в этом интерфейсе, <xref:System.Activities.Presentation.Validation.IValidationErrorService.ShowValidationErrors%2A>, который передает список объектов <xref:System.Activities.Presentation.Validation.ValidationErrorInfo>, содержащих сведения об ошибках, в журнал отладки.После реализации интерфейса сведения об ошибках получаются путем публикации экземпляра этой реализации в контексте редактирования.  
  
### Реализация интерфейса IValidationErrorService  
  
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
  
### Публикация в контексте редактирования  
  
1.  Здесь приводится код, который публикует это в контексте редактирования.  
  
    ```  
  
    wd.Context.Services.Publish<IValidationErrorService>(new DebugValidationErrorService());  
    ```