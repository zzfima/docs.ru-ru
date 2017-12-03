---
title: "Действие CommentOut"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 340204c3-f827-45fb-870e-55e2ac457ca5
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e66d1383c42310c2f61b0b3059cb8b347ad55a15
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="commentout-activity"></a><span data-ttu-id="4cba5-102">Действие CommentOut</span><span class="sxs-lookup"><span data-stu-id="4cba5-102">CommentOut Activity</span></span>
<span data-ttu-id="4cba5-103">В этом образце показан способ записи пользовательского действия, которое удаляет другие действия из пути выполнения, преобразуя эти действия в комментарии.</span><span class="sxs-lookup"><span data-stu-id="4cba5-103">This sample demonstrates how to write a custom activity that removes other activities from the path of execution, effectively commenting them out.</span></span>  
  
## <a name="the-commentout-activity"></a><span data-ttu-id="4cba5-104">Действие CommentOut</span><span class="sxs-lookup"><span data-stu-id="4cba5-104">The CommentOut Activity</span></span>  
 <span data-ttu-id="4cba5-105">Для выполнения своей задачи действие CommentOut наследует от базового класса <xref:System.Activities.CodeActivity> и реализует пустой метод <xref:System.Activities.CodeActivity.Execute%2A>.</span><span class="sxs-lookup"><span data-stu-id="4cba5-105">To achieve its goal, the CommentOut activity derives from the <xref:System.Activities.CodeActivity> base class and implements an empty <xref:System.Activities.CodeActivity.Execute%2A> method.</span></span>  
  
```  
protected override void Execute(CodeActivityContext context)  
{  
}  
```  
  
 <span data-ttu-id="4cba5-106">Класс объявляется показанным в следующем примере образом.</span><span class="sxs-lookup"><span data-stu-id="4cba5-106">The class is declared as shown in the following example.</span></span>  
  
```  
[Designer(typeof(CommentOutDesigner))]  
[ContentProperty("Body")]  
public sealed class CommentOut : CodeActivity  
```  
  
 <span data-ttu-id="4cba5-107">Атрибут `Designer` указывает класс, который реализует визуальный интерфейс действия во время разработки.</span><span class="sxs-lookup"><span data-stu-id="4cba5-107">The `Designer` attribute specifies the class that implements the visual interface of the activity at design time.</span></span> <span data-ttu-id="4cba5-108">Атрибут `ContentProperty` объявляет, что свойство `"Body"` может быть пропущено в XAML-представлении экземпляра данного действия.</span><span class="sxs-lookup"><span data-stu-id="4cba5-108">The `ContentProperty` attribute declares that the `"Body"` property can be skipped in the XAML representation of an instance of this activity.</span></span>  
  
```  
<Border x:Uid="Border_1" BorderThickness ="1">  
    <sad:WorkflowItemPresenter   
    x:Uid="sad:WorkflowItemPresenter_1" AutomationProperties.AutomationId="Body" Item="{Binding Path=ModelItem.Body, Mode=TwoWay}"  
    AllowedItemType="{x:Type sa:Activity}"  
    HintText="Drop activity here"   
    Margin="5,5,5,5" />  
</Border>  
```  
  
 <span data-ttu-id="4cba5-109">В классе конструктора XAML используется для создания настраиваемого визуального представления действия.</span><span class="sxs-lookup"><span data-stu-id="4cba5-109">In the designer class, XAML is used to create a custom visual representation of the activity.</span></span> <span data-ttu-id="4cba5-110"><xref:System.Activities.Presentation.WorkflowItemPresenter> - это класс, реализующий визуальный редактор.</span><span class="sxs-lookup"><span data-stu-id="4cba5-110"><xref:System.Activities.Presentation.WorkflowItemPresenter> is a class that provides the visual editor.</span></span>  
  
 <span data-ttu-id="4cba5-111">В область действия `CommentOut` может быть перетянуто одно действие.</span><span class="sxs-lookup"><span data-stu-id="4cba5-111">A single activity can be dropped onto the `CommentOut` activity surface.</span></span> <span data-ttu-id="4cba5-112">Если в область необходимо добавить несколько действий, сначала перетащите в нее действие последовательности.</span><span class="sxs-lookup"><span data-stu-id="4cba5-112">If you want to add multiple activities to this surface, drag a sequence activity here first.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="4cba5-113">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="4cba5-113">To use this sample</span></span>  
  
1.  <span data-ttu-id="4cba5-114">Откройте решение CommentOut.sln в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4cba5-114">Open CommentOut.sln in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="4cba5-115">Выполните сборку решения, нажав клавиши Ctrl+Shift+B.</span><span class="sxs-lookup"><span data-stu-id="4cba5-115">Compile the solution by pressing CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="4cba5-116">Запустите образец без отладки, нажав сочетание клавиш CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="4cba5-116">Start the sample without debugging by pressing CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4cba5-117">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="4cba5-117">The samples may already be installed on your machine.</span></span> <span data-ttu-id="4cba5-118">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="4cba5-118">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="4cba5-119">Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4cba5-119">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="4cba5-120">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="4cba5-120">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\CommentOut`
