---
title: Практическое руководство. Клонирование принтера
ms.date: 03/30/2017
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
ms.openlocfilehash: 09a445da068f0141b9526e0228df8be0105498c6
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59310464"
---
# <a name="how-to-clone-a-printer"></a><span data-ttu-id="6172a-102">Практическое руководство. Клонирование принтера</span><span class="sxs-lookup"><span data-stu-id="6172a-102">How to: Clone a Printer</span></span>
<span data-ttu-id="6172a-103">Большинство компаний рано или поздно купит нескольких принтеров той же модели.</span><span class="sxs-lookup"><span data-stu-id="6172a-103">Most businesses will, at some point, buy multiple printers of the same model.</span></span> <span data-ttu-id="6172a-104">Как правило они все устанавливаются с практически одинаковыми параметрами.</span><span class="sxs-lookup"><span data-stu-id="6172a-104">Typically, these are all installed with virtually identical configuration settings.</span></span> <span data-ttu-id="6172a-105">Установка каждого принтера может занимать много времени и подвержено ошибкам.</span><span class="sxs-lookup"><span data-stu-id="6172a-105">Installing each printer can be time-consuming and error prone.</span></span> <span data-ttu-id="6172a-106"><xref:System.Printing.IndexedProperties?displayProperty=nameWithType> Пространства имен и <xref:System.Printing.PrintServer.InstallPrintQueue%2A> класс, который предоставляется через Microsoft .NET Framework дает возможность мгновенно установить любое число дополнительных очередей печати, которые копируются из существующей очереди печати.</span><span class="sxs-lookup"><span data-stu-id="6172a-106">The <xref:System.Printing.IndexedProperties?displayProperty=nameWithType> namespace and the <xref:System.Printing.PrintServer.InstallPrintQueue%2A> class that are exposed with Microsoft .NET Framework makes it possible to instantly install any number of additional print queues that are cloned from an existing print queue.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6172a-107">Пример</span><span class="sxs-lookup"><span data-stu-id="6172a-107">Example</span></span>  
 <span data-ttu-id="6172a-108">В следующем примере второй очереди печати клонируется из существующей очереди печати.</span><span class="sxs-lookup"><span data-stu-id="6172a-108">In the example below, a second print queue is cloned from an existing print queue.</span></span> <span data-ttu-id="6172a-109">Второй отличающимся от первого только в его имя, расположение, порт и состояние общего доступа.</span><span class="sxs-lookup"><span data-stu-id="6172a-109">The second differs from the first only in its name, location, port, and shared status.</span></span> <span data-ttu-id="6172a-110">Ниже приведены основные действия для этого.</span><span class="sxs-lookup"><span data-stu-id="6172a-110">The major steps for doing this are as follows.</span></span>  
  
1. <span data-ttu-id="6172a-111">Создание <xref:System.Printing.PrintQueue> объект для существующего принтера, который нужно клонировать.</span><span class="sxs-lookup"><span data-stu-id="6172a-111">Create a <xref:System.Printing.PrintQueue> object for the existing printer that is going to be cloned.</span></span>  
  
2. <span data-ttu-id="6172a-112">Создание <xref:System.Printing.IndexedProperties.PrintPropertyDictionary> из <xref:System.Printing.PrintSystemObject.PropertiesCollection%2A> из <xref:System.Printing.PrintQueue>.</span><span class="sxs-lookup"><span data-stu-id="6172a-112">Create a <xref:System.Printing.IndexedProperties.PrintPropertyDictionary> from the <xref:System.Printing.PrintSystemObject.PropertiesCollection%2A> of the <xref:System.Printing.PrintQueue>.</span></span> <span data-ttu-id="6172a-113"><xref:System.Collections.DictionaryEntry.Value%2A> Каждой записи в этом словаре является объектом одного из типов, производных от <xref:System.Printing.IndexedProperties.PrintProperty>.</span><span class="sxs-lookup"><span data-stu-id="6172a-113">The <xref:System.Collections.DictionaryEntry.Value%2A> property of each entry in this dictionary is an object of one of the types derived from <xref:System.Printing.IndexedProperties.PrintProperty>.</span></span> <span data-ttu-id="6172a-114">Существует два способа установки значения объекта, содержащегося в данном словаре.</span><span class="sxs-lookup"><span data-stu-id="6172a-114">There are two ways to set the value of an entry in this dictionary.</span></span>  
  
    -   <span data-ttu-id="6172a-115">Использование словаря **удалить** и <xref:System.Printing.IndexedProperties.PrintPropertyDictionary.Add%2A> методов, чтобы удалить запись, а затем добавьте его повторно с требуемым значением.</span><span class="sxs-lookup"><span data-stu-id="6172a-115">Use the dictionary's **Remove** and <xref:System.Printing.IndexedProperties.PrintPropertyDictionary.Add%2A> methods to remove the entry and then re-add it with the desired value.</span></span>  
  
    -   <span data-ttu-id="6172a-116">Использование словаря <xref:System.Printing.IndexedProperties.PrintPropertyDictionary.SetProperty%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="6172a-116">Use the dictionary's <xref:System.Printing.IndexedProperties.PrintPropertyDictionary.SetProperty%2A> method.</span></span>  
  
     <span data-ttu-id="6172a-117">В приведенном ниже примере показаны оба способа.</span><span class="sxs-lookup"><span data-stu-id="6172a-117">The example below illustrates both ways.</span></span>  
  
3. <span data-ttu-id="6172a-118">Создание <xref:System.Printing.IndexedProperties.PrintBooleanProperty> и задайте его <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> для «IsShared» и его <xref:System.Printing.IndexedProperties.PrintBooleanProperty.Value%2A> для `true`.</span><span class="sxs-lookup"><span data-stu-id="6172a-118">Create a <xref:System.Printing.IndexedProperties.PrintBooleanProperty> object and set its <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> to "IsShared" and its <xref:System.Printing.IndexedProperties.PrintBooleanProperty.Value%2A> to `true`.</span></span>  
  
4. <span data-ttu-id="6172a-119">Используйте <xref:System.Printing.IndexedProperties.PrintBooleanProperty> объект значение <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>в записи «IsShared».</span><span class="sxs-lookup"><span data-stu-id="6172a-119">Use the <xref:System.Printing.IndexedProperties.PrintBooleanProperty> object to be the value of the <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>'s "IsShared" entry.</span></span>  
  
5. <span data-ttu-id="6172a-120">Создание <xref:System.Printing.IndexedProperties.PrintStringProperty> и задайте его <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> для «ShareName» и его <xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A> — соответствующую <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="6172a-120">Create a <xref:System.Printing.IndexedProperties.PrintStringProperty> object and set its <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> to "ShareName" and its <xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A> to an appropriate <xref:System.String>.</span></span>  
  
6. <span data-ttu-id="6172a-121">Используйте <xref:System.Printing.IndexedProperties.PrintStringProperty> объект значение <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>в записи «Ресурс».</span><span class="sxs-lookup"><span data-stu-id="6172a-121">Use the <xref:System.Printing.IndexedProperties.PrintStringProperty> object to be the value of the <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>'s "ShareName" entry.</span></span>  
  
7. <span data-ttu-id="6172a-122">Создайте другой <xref:System.Printing.IndexedProperties.PrintStringProperty> и задайте его <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> «Расположение» и его <xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A> — соответствующую <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="6172a-122">Create another <xref:System.Printing.IndexedProperties.PrintStringProperty> object and set its <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> to "Location" and its <xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A> to an appropriate <xref:System.String>.</span></span>  
  
8. <span data-ttu-id="6172a-123">Используйте второй <xref:System.Printing.IndexedProperties.PrintStringProperty> объект значение <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>в записи «Местоположение».</span><span class="sxs-lookup"><span data-stu-id="6172a-123">Use the second <xref:System.Printing.IndexedProperties.PrintStringProperty> object to be the value of the <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>'s "Location" entry.</span></span>  
  
9. <span data-ttu-id="6172a-124">Создайте массив <xref:System.String>s.</span><span class="sxs-lookup"><span data-stu-id="6172a-124">Create an array of <xref:System.String>s.</span></span> <span data-ttu-id="6172a-125">Каждый элемент является имя порта на сервере.</span><span class="sxs-lookup"><span data-stu-id="6172a-125">Each item is the name of a port on the server.</span></span>  
  
10. <span data-ttu-id="6172a-126">Используйте <xref:System.Printing.PrintServer.InstallPrintQueue%2A> для установки нового принтера с новыми значениями.</span><span class="sxs-lookup"><span data-stu-id="6172a-126">Use <xref:System.Printing.PrintServer.InstallPrintQueue%2A> to install the new printer with the new values.</span></span>  
  
 <span data-ttu-id="6172a-127">Пример приведен ниже.</span><span class="sxs-lookup"><span data-stu-id="6172a-127">An example is below.</span></span>  
  
 [!code-csharp[ClonePrinter#ClonePrinter](~/samples/snippets/csharp/VS_Snippets_Wpf/ClonePrinter/CSharp/Program.cs#cloneprinter)]
 [!code-vb[ClonePrinter#ClonePrinter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ClonePrinter/visualbasic/program.vb#cloneprinter)]  
  
## <a name="see-also"></a><span data-ttu-id="6172a-128">См. также</span><span class="sxs-lookup"><span data-stu-id="6172a-128">See also</span></span>

- <xref:System.Printing.IndexedProperties>
- <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>
- <xref:System.Printing.LocalPrintServer>
- <xref:System.Printing.PrintQueue>
- <xref:System.Collections.DictionaryEntry>
- [<span data-ttu-id="6172a-129">Документы в WPF</span><span class="sxs-lookup"><span data-stu-id="6172a-129">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="6172a-130">Общие сведения о печати</span><span class="sxs-lookup"><span data-stu-id="6172a-130">Printing Overview</span></span>](printing-overview.md)
