---
title: Практическое руководство. Клонирование принтера
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- print queues [WPF]
- cloning printers [WPF]
- printers [WPF], cloning
- print queues [WPF], cloning
- cloning print queues [WPF]
ms.assetid: dd6997c9-fe04-40f8-88a6-92e3ac0889eb
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9ffb9f5ab8e7b768d888f5f2800fae668e47bfc3
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2018
---
# <a name="how-to-clone-a-printer"></a><span data-ttu-id="1ea35-102">Практическое руководство. Клонирование принтера</span><span class="sxs-lookup"><span data-stu-id="1ea35-102">How to: Clone a Printer</span></span>
<span data-ttu-id="1ea35-103">Большинство компаний в определенный момент купит нескольких принтеров той же модели.</span><span class="sxs-lookup"><span data-stu-id="1ea35-103">Most businesses will, at some point, buy multiple printers of the same model.</span></span> <span data-ttu-id="1ea35-104">Как правило они все вместе устанавливаются с практически одинаковыми параметрами.</span><span class="sxs-lookup"><span data-stu-id="1ea35-104">Typically, these are all installed with virtually identical configuration settings.</span></span> <span data-ttu-id="1ea35-105">Установка каждого принтера может занять много времени и подвержены ошибкам.</span><span class="sxs-lookup"><span data-stu-id="1ea35-105">Installing each printer can be time-consuming and error prone.</span></span> <span data-ttu-id="1ea35-106"><xref:System.Printing.IndexedProperties?displayProperty=nameWithType> Пространства имен и <xref:System.Printing.PrintServer.InstallPrintQueue%2A> класс, который предоставляется через Microsoft .NET Framework дает возможность мгновенно установить любое число дополнительных очередей печати, которые будут скопированы из существующей очереди печати.</span><span class="sxs-lookup"><span data-stu-id="1ea35-106">The <xref:System.Printing.IndexedProperties?displayProperty=nameWithType> namespace and the <xref:System.Printing.PrintServer.InstallPrintQueue%2A> class that are exposed with Microsoft .NET Framework makes it possible to instantly install any number of additional print queues that are cloned from an existing print queue.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1ea35-107">Пример</span><span class="sxs-lookup"><span data-stu-id="1ea35-107">Example</span></span>  
 <span data-ttu-id="1ea35-108">В приведенном ниже примере вторая очередь печати клонируется из существующей очереди печати.</span><span class="sxs-lookup"><span data-stu-id="1ea35-108">In the example below, a second print queue is cloned from an existing print queue.</span></span> <span data-ttu-id="1ea35-109">Второй отличающимся от первого только в его имя, расположение, порт и состояние общего доступа.</span><span class="sxs-lookup"><span data-stu-id="1ea35-109">The second differs from the first only in its name, location, port, and shared status.</span></span> <span data-ttu-id="1ea35-110">Ниже приведены основные действия по созданию.</span><span class="sxs-lookup"><span data-stu-id="1ea35-110">The major steps for doing this are as follows.</span></span>  
  
1.  <span data-ttu-id="1ea35-111">Создание <xref:System.Printing.PrintQueue> объекта для существующего принтера, который требуется создать точную копию.</span><span class="sxs-lookup"><span data-stu-id="1ea35-111">Create a <xref:System.Printing.PrintQueue> object for the existing printer that is going to be cloned.</span></span>  
  
2.  <span data-ttu-id="1ea35-112">Создание <xref:System.Printing.IndexedProperties.PrintPropertyDictionary> из <xref:System.Printing.PrintSystemObject.PropertiesCollection%2A> из <xref:System.Printing.PrintQueue>.</span><span class="sxs-lookup"><span data-stu-id="1ea35-112">Create a <xref:System.Printing.IndexedProperties.PrintPropertyDictionary> from the <xref:System.Printing.PrintSystemObject.PropertiesCollection%2A> of the <xref:System.Printing.PrintQueue>.</span></span> <span data-ttu-id="1ea35-113"><xref:System.Collections.DictionaryEntry.Value%2A> Каждой записи в этом словаре является объектом одного из типов, производных от <xref:System.Printing.IndexedProperties.PrintProperty>.</span><span class="sxs-lookup"><span data-stu-id="1ea35-113">The <xref:System.Collections.DictionaryEntry.Value%2A> property of each entry in this dictionary is an object of one of the types derived from <xref:System.Printing.IndexedProperties.PrintProperty>.</span></span> <span data-ttu-id="1ea35-114">Существует два способа задать значение записи в этом словаре.</span><span class="sxs-lookup"><span data-stu-id="1ea35-114">There are two ways to set the value of an entry in this dictionary.</span></span>  
  
    -   <span data-ttu-id="1ea35-115">Использование словаря **удалить** и <xref:System.Printing.IndexedProperties.PrintPropertyDictionary.Add%2A> методов, чтобы удалить запись, а затем снова добавьте его с требуемым значением.</span><span class="sxs-lookup"><span data-stu-id="1ea35-115">Use the dictionary's **Remove** and <xref:System.Printing.IndexedProperties.PrintPropertyDictionary.Add%2A> methods to remove the entry and then re-add it with the desired value.</span></span>  
  
    -   <span data-ttu-id="1ea35-116">Использование словаря <xref:System.Printing.IndexedProperties.PrintPropertyDictionary.SetProperty%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="1ea35-116">Use the dictionary's <xref:System.Printing.IndexedProperties.PrintPropertyDictionary.SetProperty%2A> method.</span></span>  
  
     <span data-ttu-id="1ea35-117">В приведенном ниже примере показаны оба способа.</span><span class="sxs-lookup"><span data-stu-id="1ea35-117">The example below illustrates both ways.</span></span>  
  
3.  <span data-ttu-id="1ea35-118">Создание <xref:System.Printing.IndexedProperties.PrintBooleanProperty> и задайте его <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> для «IsShared» и его <xref:System.Printing.IndexedProperties.PrintBooleanProperty.Value%2A> для `true`.</span><span class="sxs-lookup"><span data-stu-id="1ea35-118">Create a <xref:System.Printing.IndexedProperties.PrintBooleanProperty> object and set its <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> to "IsShared" and its <xref:System.Printing.IndexedProperties.PrintBooleanProperty.Value%2A> to `true`.</span></span>  
  
4.  <span data-ttu-id="1ea35-119">Используйте <xref:System.Printing.IndexedProperties.PrintBooleanProperty> объект, который будет значение <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>в записи «IsShared».</span><span class="sxs-lookup"><span data-stu-id="1ea35-119">Use the <xref:System.Printing.IndexedProperties.PrintBooleanProperty> object to be the value of the <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>'s "IsShared" entry.</span></span>  
  
5.  <span data-ttu-id="1ea35-120">Создание <xref:System.Printing.IndexedProperties.PrintStringProperty> и задайте его <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> для «ShareName» и его <xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A> — соответствующую <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="1ea35-120">Create a <xref:System.Printing.IndexedProperties.PrintStringProperty> object and set its <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> to "ShareName" and its <xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A> to an appropriate <xref:System.String>.</span></span>  
  
6.  <span data-ttu-id="1ea35-121">Используйте <xref:System.Printing.IndexedProperties.PrintStringProperty> объект, который будет значение <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>в записи «ShareName».</span><span class="sxs-lookup"><span data-stu-id="1ea35-121">Use the <xref:System.Printing.IndexedProperties.PrintStringProperty> object to be the value of the <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>'s "ShareName" entry.</span></span>  
  
7.  <span data-ttu-id="1ea35-122">Создайте другой <xref:System.Printing.IndexedProperties.PrintStringProperty> и задайте его <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> для «Местоположение» и его <xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A> — соответствующую <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="1ea35-122">Create another <xref:System.Printing.IndexedProperties.PrintStringProperty> object and set its <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> to "Location" and its <xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A> to an appropriate <xref:System.String>.</span></span>  
  
8.  <span data-ttu-id="1ea35-123">Используйте второй <xref:System.Printing.IndexedProperties.PrintStringProperty> объект, который будет значение <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>в записи «Местоположение».</span><span class="sxs-lookup"><span data-stu-id="1ea35-123">Use the second <xref:System.Printing.IndexedProperties.PrintStringProperty> object to be the value of the <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>'s "Location" entry.</span></span>  
  
9. <span data-ttu-id="1ea35-124">Создайте массив <xref:System.String>s.</span><span class="sxs-lookup"><span data-stu-id="1ea35-124">Create an array of <xref:System.String>s.</span></span> <span data-ttu-id="1ea35-125">Каждый элемент — это имя порта на сервере.</span><span class="sxs-lookup"><span data-stu-id="1ea35-125">Each item is the name of a port on the server.</span></span>  
  
10. <span data-ttu-id="1ea35-126">Используйте <xref:System.Printing.PrintServer.InstallPrintQueue%2A> для установки нового принтера с новыми значениями.</span><span class="sxs-lookup"><span data-stu-id="1ea35-126">Use <xref:System.Printing.PrintServer.InstallPrintQueue%2A> to install the new printer with the new values.</span></span>  
  
 <span data-ttu-id="1ea35-127">Пример приведен ниже.</span><span class="sxs-lookup"><span data-stu-id="1ea35-127">An example is below.</span></span>  
  
 [!code-csharp[ClonePrinter#ClonePrinter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ClonePrinter/CSharp/Program.cs#cloneprinter)]
 [!code-vb[ClonePrinter#ClonePrinter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ClonePrinter/visualbasic/program.vb#cloneprinter)]  
  
## <a name="see-also"></a><span data-ttu-id="1ea35-128">См. также</span><span class="sxs-lookup"><span data-stu-id="1ea35-128">See Also</span></span>  
 <xref:System.Printing.IndexedProperties>  
 <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>  
 <xref:System.Printing.LocalPrintServer>  
 <xref:System.Printing.PrintQueue>  
 <xref:System.Collections.DictionaryEntry>  
 [<span data-ttu-id="1ea35-129">Документы в WPF</span><span class="sxs-lookup"><span data-stu-id="1ea35-129">Documents in WPF</span></span>](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [<span data-ttu-id="1ea35-130">Общие сведения о печати</span><span class="sxs-lookup"><span data-stu-id="1ea35-130">Printing Overview</span></span>](../../../../docs/framework/wpf/advanced/printing-overview.md)
