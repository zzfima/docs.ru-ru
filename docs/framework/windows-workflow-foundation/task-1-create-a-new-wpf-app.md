---
title: "Задача 1. Создание нового приложения Windows Presentation Foundation"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 270eaeba-9492-4532-af9f-403ce5c9935b
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 89c929e71a2d64673f158f81c85d04c3443800ac
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="task-1-create-a-new-windows-presentation-foundation-application"></a>Задача 1. Создание нового приложения Windows Presentation Foundation
В данной задаче необходимо создать пустое приложение [!INCLUDE[avalon1](../../../includes/avalon1-md.md)], используя шаблон WPF Application Visual Studio, и добавить ссылки на соответствующие сборки рабочего процесса [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)].  
  
### <a name="to-create-the-wpf-application-project"></a>Создание проекта приложения WPF  
  
1.  Откройте [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)] и на **файл** последовательно выберите пункты **New**, а затем нажмите кнопку **проекта**.  
  
2.  В **новый проект** диалогового окна выберите либо **Visual C#** или **Visual Basic** из **установленные шаблоны** на левой стороне панели поле. Если язык не отображается, разверните узел **другие языки**.  
  
3.  Выберите **Windows** в **установленные шаблоны** области.  
  
4.  Убедитесь, что в верхней области (значение по умолчанию) **.NET Framework 4** был выбранного в раскрывающемся списке, а затем выберите **приложение WPF**.  
  
5.  Задайте имя проекта для **HostingApplication** в нижней части окна.  
  
6.  Задайте имя решения **RehostingTheDesigner**.  
  
7.  Нажмите кнопку **ОК** Создание проекта приложения. [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)] создает основной пользовательский интерфейс WPF для приложения и включает в него соответствующий XAML и файлы с фоновым кодом.  
  
8.  Добавьте ссылки на **WorkflowModel** сборки. Для этого в **обозревателе решений**, щелкните правой кнопкой мыши **HostingApplication** проект и выберите **добавить ссылку**.  
  
9. В **добавить ссылку** диалоговое окно, нажмите кнопку **.NET** удерживайте нажатой клавишу CTRL, выберите следующие сборки и нажмите кнопку **ОК**:  
  
    -   System.Activities  
  
    -   System.Activities.Presentation  
  
    -   System.Activities.Core.Presentation  
  
10. Нажмите кнопку **ОК**.  
  
11. В разделе [задача 2: размещение конструктора рабочих процессов](../../../docs/framework/windows-workflow-foundation/task-2-host-the-workflow-designer.md) чтобы узнать, как разместить полотно конструктора в конструкторе рабочего процесса.  
  
## <a name="see-also"></a>См. также  
 [Отдельное размещение конструктора рабочих процессов](../../../docs/framework/windows-workflow-foundation/rehosting-the-workflow-designer.md)  
 [Задача 2. Размещение конструктора рабочих процессов](../../../docs/framework/windows-workflow-foundation/task-2-host-the-workflow-designer.md)
