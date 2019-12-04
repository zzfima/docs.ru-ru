---
title: Как отображать ошибки проверок в повторно размещенном конструкторе
ms.date: 03/30/2017
ms.assetid: 5aa8fb53-8f75-433b-bc06-7c7d33583d5d
ms.openlocfilehash: bd0c2c10665de4bc3364938167101655a9bdd056
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74716282"
---
# <a name="how-to-display-validation-errors-in-a-rehosted-designer"></a>Как отображать ошибки проверок в повторно размещенном конструкторе
В этом разделе описывается получение и публикация ошибок проверки в переразмещенной конструктор рабочих процессов Windows. Это предоставляет процедуру подтверждения того, что рабочий процесс в повторно размещенном конструкторе является допустимым.  
  
 Эта задача имеет две части. Первой задачей является предоставление реализации <xref:System.Activities.Presentation.Validation.IValidationErrorService>.  Имеется один очень важный метод, реализуемый в этом интерфейсе, <xref:System.Activities.Presentation.Validation.IValidationErrorService.ShowValidationErrors%2A>, который передает список объектов <xref:System.Activities.Presentation.Validation.ValidationErrorInfo>, содержащих сведения об ошибках, в журнал отладки.  После реализации интерфейса сведения об ошибках получаются путем публикации экземпляра этой реализации в контексте редактирования.  
  
### <a name="implement-the-ivalidationerrorservice-interface"></a>Реализация интерфейса IValidationErrorService  
  
1. Здесь приводится образец кода для простой реализации, которая записывает ошибки проверки в журнал отладки.  
  
    ```csharp  
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
                errors.ToList().ForEach(vei => Debug.WriteLine($"Error: {vei.Message}"));  
            }  
        }  
    }  
    ```  
  
### <a name="publishing-to-the-editing-context"></a>Публикация в контексте редактирования  
  
1. Здесь приводится код, который публикует это в контексте редактирования.  
  
    ```csharp  
    wd.Context.Services.Publish<IValidationErrorService>(new DebugValidationErrorService());  
    ```
