---
title: Использование действия из .NET Framework 3.0 или .NET Framework 3.5 в рабочем процессе .NET Framework 4.5
ms.date: 03/30/2017
ms.assetid: 6c53fd4c-5dd0-4fb4-ab6b-111302629548
ms.openlocfilehash: ab2e93918617bd1ca21fb32878d446db0dd2ef16
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33514903"
---
# <a name="using-a-net-framework-30-or-net-framework-35-activity-in-a-net-framework-45-workflow"></a>Использование действия из .NET Framework 3.0 или .NET Framework 3.5 в рабочем процессе .NET Framework 4.5
<xref:System.Activities.Statements.Interop> Действия позволяет выполнять действие .NET Framework 3.0 Windows Workflow Foundation (WF) в [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)] рабочего процесса. В этом образце показано, как использовать действие <xref:System.Activities.Statements.Interop> для передачи строки в качестве аргумента для пользовательского действия [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)].  
  
## <a name="to-use-this-sample"></a>Использование этого образца  
  
1.  Используя [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], откройте файл решения SimpleInterop.sln.  
  
2.  Для построения решения нажмите CTRL+SHIFT+B.  
  
3.  Чтобы запустить решение, нажмите клавиши CTRL+F5.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцов. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Migration\SimpleInterop`  
  
## <a name="see-also"></a>См. также
