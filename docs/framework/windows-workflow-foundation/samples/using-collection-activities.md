---
title: "Использование действий с коллекциями"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e1977cf8-1695-4071-b946-7046fe39601e
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: be7615441f29046fc1a469e3cace86267fc6c031
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="using-collection-activities"></a><span data-ttu-id="ca549-102">Использование действий с коллекциями</span><span class="sxs-lookup"><span data-stu-id="ca549-102">Using Collection Activities</span></span>
<span data-ttu-id="ca549-103">В этом образце демонстрируется использование действий коллекции (<xref:System.Activities.Statements.AddToCollection%601>, <xref:System.Activities.Statements.ClearCollection%601>, <xref:System.Activities.Statements.ExistsInCollection%601> и <xref:System.Activities.Statements.RemoveFromCollection%601>) с классом, реализующим интерфейс <xref:System.Collections.ICollection>, и создание пользовательского действия, которое выполняет итерацию по коллекции для распечатки содержания каждого из элементов коллекции.</span><span class="sxs-lookup"><span data-stu-id="ca549-103">This sample demonstrates how to use the collection activities (<xref:System.Activities.Statements.AddToCollection%601>, <xref:System.Activities.Statements.ClearCollection%601>, <xref:System.Activities.Statements.ExistsInCollection%601>, and <xref:System.Activities.Statements.RemoveFromCollection%601>) with a class that implements the <xref:System.Collections.ICollection> interface and how to create a custom activity that iterates over a collection to print out the contents of each element in the collection.</span></span> <span data-ttu-id="ca549-104">Пользовательское действие, называемое `PrintCollection`, выводит на консоль элементы коллекции с названием `Numbers`.</span><span class="sxs-lookup"><span data-stu-id="ca549-104">The custom activity, which is named `PrintCollection`, prints to the console the item members of a collection named `Numbers`.</span></span>  
  
 <span data-ttu-id="ca549-105">В следующей таблице представлены четыре действия, посредством которых осуществляется управление коллекциями в рабочих процессах.</span><span class="sxs-lookup"><span data-stu-id="ca549-105">The following table describes the four activities that provide collection manipulation for workflows.</span></span>  
  
|<span data-ttu-id="ca549-106">Название действия</span><span class="sxs-lookup"><span data-stu-id="ca549-106">Activity name</span></span>|<span data-ttu-id="ca549-107">Описание</span><span class="sxs-lookup"><span data-stu-id="ca549-107">Description</span></span>|  
|-------------------|-----------------|  
|<xref:System.Activities.Statements.AddToCollection%601>|<span data-ttu-id="ca549-108">Добавляет элемент в коллекцию.</span><span class="sxs-lookup"><span data-stu-id="ca549-108">Adds an item to a collection.</span></span>|  
|<xref:System.Activities.Statements.ClearCollection%601>|<span data-ttu-id="ca549-109">Очищает коллекцию, удаляя все элементы.</span><span class="sxs-lookup"><span data-stu-id="ca549-109">Clears all items in a collection</span></span>|  
|<xref:System.Activities.Statements.ExistsInCollection%601>|<span data-ttu-id="ca549-110">Если элемент присутствует в коллекции, возвращает `true`.</span><span class="sxs-lookup"><span data-stu-id="ca549-110">Returns `true` if specified item exists in collection.</span></span>|  
|<xref:System.Activities.Statements.RemoveFromCollection%601>|<span data-ttu-id="ca549-111">Удаляет элемент из коллекции.</span><span class="sxs-lookup"><span data-stu-id="ca549-111">Removes an item from a collection.</span></span>|  
  
 <span data-ttu-id="ca549-112">Образец состоит из двух решений, одно из которых находится в каталоге CodedWorkflow, а другое - в каталоге DesignerWorkflow.</span><span class="sxs-lookup"><span data-stu-id="ca549-112">The sample consists of two solutions, one under the CodedWorkflow directory and the other under the DesignerWorkflow directory.</span></span> <span data-ttu-id="ca549-113">Они демонстрируют два разных способа использования действий для выполнения одинаковых задач.</span><span class="sxs-lookup"><span data-stu-id="ca549-113">They demonstrate two different ways of using the activities for the same purposes.</span></span>  
  
|<span data-ttu-id="ca549-114">Решение</span><span class="sxs-lookup"><span data-stu-id="ca549-114">Solution</span></span>|<span data-ttu-id="ca549-115">Описание</span><span class="sxs-lookup"><span data-stu-id="ca549-115">Description</span></span>|<span data-ttu-id="ca549-116">Основные файлы</span><span class="sxs-lookup"><span data-stu-id="ca549-116">Main Files</span></span>|  
|-|-|-|  
|<span data-ttu-id="ca549-117">CodedWorkflow</span><span class="sxs-lookup"><span data-stu-id="ca549-117">CodedWorkflow</span></span>|<span data-ttu-id="ca549-118">Образец клиентского приложения, демонстрирующий, как вызывать действия коллекции программным образом.</span><span class="sxs-lookup"><span data-stu-id="ca549-118">Sample client application that demonstrates how to invoke the collection activities programmatically.</span></span>|<span data-ttu-id="ca549-119">**PrintCollection.cs**: вспомогательное действие для вывода каждого элемента в коллекции на консоль.</span><span class="sxs-lookup"><span data-stu-id="ca549-119">**PrintCollection.cs**: helper activity to print out to the console every item in a collection.</span></span><br /><br /> <span data-ttu-id="ca549-120">**Program.cs**: программным образом создает последовательное действие, содержащее ряд действий коллекции и выполняет его.</span><span class="sxs-lookup"><span data-stu-id="ca549-120">**Program.cs**: programmatically builds a sequence activity that contains a series of collection activities, and executes it.</span></span>|  
|<span data-ttu-id="ca549-121">DesignerWorkflow</span><span class="sxs-lookup"><span data-stu-id="ca549-121">DesignerWorkflow</span></span>|<span data-ttu-id="ca549-122">Образец клиентского приложения, демонстрирующий, как декларативно использовать действия коллекции в конструкторе рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="ca549-122">Sample client application that demonstrates how to use the collection activities declaratively in the workflow designer.</span></span>|<span data-ttu-id="ca549-123">**CollectionWorkflow.xaml**: рабочий процесс, созданный декларативно с конструктором, использующим действия коллекции.</span><span class="sxs-lookup"><span data-stu-id="ca549-123">**CollectionWorkflow.xaml**: a workflow created declaratively with the designer that uses the collection activities.</span></span><br /><br /> <span data-ttu-id="ca549-124">**PrintCollection.cs**: вспомогательное действие для вывода каждого элемента в коллекции на консоль.</span><span class="sxs-lookup"><span data-stu-id="ca549-124">**PrintCollection.cs**: helper activity to print out to the console every item in a collection.</span></span><br /><br /> <span data-ttu-id="ca549-125">**Program.cs**: вызывает рабочий процесс, описанный в CollectionWorkflow.xaml.</span><span class="sxs-lookup"><span data-stu-id="ca549-125">**Program.cs**: invokes the workflow described in CollectionWorkflow.xaml.</span></span>|  
  
 <span data-ttu-id="ca549-126">При демонстрации элементы коллекции `Numbers` выводятся на консоль с использованием определенного пользователем действия под названием `PrintCollection`.</span><span class="sxs-lookup"><span data-stu-id="ca549-126">In the demonstration, the item members of collection `Numbers` are printed on the console using a custom-defined activity called `PrintCollection`.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="ca549-127">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="ca549-127">To use this sample</span></span>  
  
1.  <span data-ttu-id="ca549-128">Используя [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], откройте файл решения Collection.sln.</span><span class="sxs-lookup"><span data-stu-id="ca549-128">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the Collection.sln solution file.</span></span>  
  
2.  <span data-ttu-id="ca549-129">Для построения решения нажмите CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="ca549-129">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="ca549-130">Чтобы запустить решение, нажмите клавиши CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="ca549-130">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ca549-131">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="ca549-131">The samples may already be installed on your machine.</span></span> <span data-ttu-id="ca549-132">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="ca549-132">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="ca549-133">Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ca549-133">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ca549-134">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="ca549-134">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\Collection`