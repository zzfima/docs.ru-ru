---
title: Использование области редактирования
ms.date: 03/30/2017
ms.assetid: 79306f9e-318b-4687-9863-8b93d1841716
ms.openlocfilehash: 3e99610fda78e50f6d6eb72c38ecc82bdc96b5a2
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715553"
---
# <a name="using-editing-scope"></a>Использование области редактирования
В этом образце показано, как организовать набор изменений в пакет, чтобы отменить их как одну атомарную операцию. По умолчанию действия, выполняемые автором конструктора действий, автоматически интегрируются в систему отмены и повтора.  
  
## <a name="demonstrates"></a>Демонстрации  
 Редактирование области, отмена и повтор.  
  
## <a name="discussion"></a>Обсуждение  
 В этом образце показано, как организовать набор изменений в дереве <xref:System.Activities.Presentation.Model.ModelItem> в рамках одной единицы работы. Обратите внимание, что при привязке к <xref:System.Activities.Presentation.Model.ModelItem> значений непосредственно из конструктора WPF изменения вносятся автоматически. В данном образце показано, что следует делать, когда организуемые в пакет изменения производятся посредством императивного кода, а не единичным изменением.  
  
 В данном образце добавляются три действия. Когда начинается редактирование, для экземпляра <xref:System.Activities.Presentation.Model.ModelItem.BeginEdit%2A> вызывается метод <xref:System.Activities.Presentation.Model.ModelItem>. Изменения, внесенные в дерево <xref:System.Activities.Presentation.Model.ModelItem> в рамках данной области редактирования, организуются в пакет. Команда <xref:System.Activities.Presentation.Model.ModelItem.BeginEdit%2A> возвращает объект <xref:System.Activities.Presentation.Model.EditingScope>, с помощью которого можно управлять данным экземпляром. Чтобы зафиксировать или восстановить область редактирования, можно вызвать метод <xref:System.Activities.Presentation.Model.EditingScope.OnComplete%2A> или <xref:System.Activities.Presentation.Model.EditingScope.OnRevert%2A>.  
  
 Кроме того, можно вкладывать друг в друга объекты <xref:System.Activities.Presentation.Model.EditingScope>, которые позволяют отслеживать несколько групп изменений как часть более крупной области изменений, и которые можно регулировать вручную. Сценарий, использующий эту возможность, полезен при необходимости по отдельности фиксировать или восстанавливать изменения из нескольких диалогов, которые считаются единичными атомарными операциями. В данном образце области редактирования накапливаются с использованием коллекции <xref:System.Collections.ObjectModel.ObservableCollection%601> объектов типа <xref:System.Activities.Presentation.Model.ModelEditingScope>. Коллекция <xref:System.Collections.ObjectModel.ObservableCollection%601> используется таким образом, чтобы глубину вложения можно было контролировать через интерфейс конструктора.  
  
## <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1. Постройте и запустите образец, после чего модифицируйте рабочий процесс при помощи кнопок слева.  
  
2. Щелкните **открыть область редактирования**.  
  
    1. Эта команда вызывает метод <xref:System.Activities.Presentation.Model.ModelItem.BeginEdit%2A>, создающий область редактирования и отправляющий ее в стек редактирования.  
  
    2. Затем к выбранному элементу <xref:System.Activities.Presentation.Model.ModelItem> добавляются три действия. Стоит заметить, что если область редактирования открывалась не с помощью метода <xref:System.Activities.Presentation.Model.ModelItem.BeginEdit%2A>, на полотне конструктора появятся три новых действия. Пока эта операция еще находится в очереди <xref:System.Activities.Presentation.Model.EditingScope>, конструктор не обновляется.  
  
3. Нажмите кнопку **Закрыть область редактирования** , чтобы зафиксировать область редактирования. Три действия появятся в конструкторе.  
  
> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples. Этот образец расположен в следующем каталоге.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\CustomActivityDesigners\UsingEditingScope`
