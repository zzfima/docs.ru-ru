---
title: Задача 1. Создание нового приложения Windows Presentation Foundation
ms.date: 03/30/2017
ms.assetid: 270eaeba-9492-4532-af9f-403ce5c9935b
ms.openlocfilehash: dae523714862ed36d36e65b51be62acff9b17f51
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59193405"
---
# <a name="task-1-create-a-new-windows-presentation-foundation-application"></a>Задача 1. Создание нового приложения Windows Presentation Foundation
В этой задаче будет создать пустое приложение Windows Presentation Foundation (WPF), используя шаблон WPF Application Visual Studio и добавьте ссылки на соответствующие [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] сборки рабочих процессов.  
  
### <a name="to-create-the-wpf-application-project"></a>Создание проекта приложения WPF  
  
1.  Откройте Visual Studio и на **файл** последовательно выберите пункты **New**, а затем нажмите кнопку **проекта**.  
  
2.  В **новый проект** диалогового окна выберите либо **Visual C#**  или **Visual Basic** из **установленные шаблоны** в левую панель части поля. Если язык не отображается, найдите его в разделе **другие языки**.  
  
3.  Выберите **Windows** в **установленные шаблоны** области.  
  
4.  Убедитесь, что в верхней области (значение по умолчанию) **.NET Framework 4** была в поле с раскрывающимся списком, а затем выберите **приложение WPF**.  
  
5.  Задайте имя проекта, который **HostingApplication** в нижней части окна.  
  
6.  Задайте имя решения **RehostingTheDesigner**.  
  
7.  Нажмите кнопку **ОК** Создание проекта приложения. Visual Studio создает основной пользовательский Интерфейс WPF для приложения и включает в себя соответствующий XAML и файлы с выделенным кодом.  
  
8.  Добавьте ссылки на **WorkflowModel** сборки. Для этого в **обозревателе решений**, щелкните правой кнопкой мыши **HostingApplication** проекта и выберите **добавить ссылку**.  
  
9. В **добавить ссылку** диалоговом окне щелкните **.NET** вкладке, удерживая нажатой клавишу CTRL, выберите следующие сборки и нажмите кнопку **ОК**:  
  
    -   System.Activities  
  
    -   System.Activities.Presentation  
  
    -   System.Activities.Core.Presentation  
  
10. Нажмите кнопку **ОК**.  
  
11. См. в разделе [задача 2: Размещение конструктора рабочих процессов](task-2-host-the-workflow-designer.md) Дополнительные сведения о размещении визуальной разработки конструктора рабочих процессов.  
  
## <a name="see-also"></a>См. также

- [Повторное размещение конструктора рабочих процессов](rehosting-the-workflow-designer.md)
- [Задача 2. Размещение конструктора рабочих процессов](task-2-host-the-workflow-designer.md)
