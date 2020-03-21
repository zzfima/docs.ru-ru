---
title: Программирование дерева элементов модели
ms.date: 03/30/2017
ms.assetid: 0229efde-19ac-4bdc-a187-c6227a7bd1a5
ms.openlocfilehash: f14b140fdac95f3763cc5625841a725793876fa4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142697"
---
# <a name="programming-model-item-tree"></a>Программирование дерева элементов модели
В этом примере показано, как перемещаться по <xref:System.Activities.Presentation.Model.ModelItem> дереву с помощью декларативного связывания данных из Представления Windows Foundation (WPF) Tree View.

## <a name="sample-details"></a>Подробные сведения об образце
 Дерево <xref:System.Activities.Presentation.Model.ModelItem> — это абстракция, используемая инфраструктурой Конструктора рабочего процесса Windows для разоблачения данных об отредактированном базовом экземпляре. Следующая иллюстрация представляет собой изображение различных уровней инфраструктуры в проектировщике рабочего процесса.

 ![Диаграмма, отображая архитектуру рабочего процесса designer.](./media/programming-model-item-tree/workflow-designer-architecture.jpg)

 Элемент <xref:System.Activities.Presentation.Model.ModelItem> состоит из указателя базового значения, а также коллекции объектов <xref:System.Activities.Presentation.Model.ModelProperty>. Объект <xref:System.Activities.Presentation.Model.ModelProperty> в свою очередь включает данные, такие как имя и тип свойства, и указатель значения, который в свою очередь является еще одним элементом <xref:System.Activities.Presentation.Model.ModelItem>. Преобразователь значений используется для манипуляции некоторыми элементами <xref:System.Activities.Presentation.Model.ModelItem>, возвращаемыми свойством <xref:System.Activities.Presentation.Model.ModelProperty>, чтобы они правильно отображались в представлении дерева. Далее в образце показано, как императивно программировать с использованием дерева <xref:System.Activities.Presentation.Model.ModelItem> при помощи императивных инструкций, в соответствии со следующим примером.

```csharp
ModelItem mi = wd.Context.Services.GetService<ModelService>().Root;
ModelProperty mp = mi.Properties["Activities"];
mp.Collection.Add(new Persist());
ModelItem justAdded = mp.Collection.Last();
justAdded.Properties["DisplayName"].SetValue("new name");
```

#### <a name="to-use-this-sample"></a>Использование этого образца

1. Откройте решение ProgrammingModelItemTree.sln в Visual Studio 2010.

2. Создайте решение, выбрав **решение Build** из меню **Build.**

3. Нажмите клавишу F5 для запуска приложения. Затем отображается форма WPF.

4. Нажмите кнопку **Load WF,** чтобы загрузить <xref:System.Activities.Presentation.Model.ModelItem> и привязать ее к представлению дерева.

5. Нажатие кнопки **«Дерево изменения модели изменения»** выполняет предыдущий код, чтобы добавить элемент в дерево и установить свойство.

> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Если этого каталога не существует, перейдите в [Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) Образцы для .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) чтобы загрузить все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцы. Этот образец расположен в следующем каталоге.  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Designer\ProgrammingModelItemTree`  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Data.IValueConverter>
