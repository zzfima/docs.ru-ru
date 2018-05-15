---
title: Практическое руководство. Получение свойств объекта системы печати без отражения
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PrintSystemObject [WPF], getting properties
ms.assetid: 43560f28-183d-41c1-b9d1-de7c2552273e
ms.openlocfilehash: 1fa8029b8245aef5e10e9082a1038fd89fc1c84e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-get-print-system-object-properties-without-reflection"></a><span data-ttu-id="8dbc0-102">Практическое руководство. Получение свойств объекта системы печати без отражения</span><span class="sxs-lookup"><span data-stu-id="8dbc0-102">How to: Get Print System Object Properties Without Reflection</span></span>
<span data-ttu-id="8dbc0-103">Использование отражения для перечисления свойств (и типов этих свойств) в объекте может снизить производительность приложения.</span><span class="sxs-lookup"><span data-stu-id="8dbc0-103">Using reflection to itemize the properties (and the types of those properties) on an object can slow application performance.</span></span> <span data-ttu-id="8dbc0-104"><xref:System.Printing.IndexedProperties> Пространство имен служит для передачи этой информации с помощью отражения.</span><span class="sxs-lookup"><span data-stu-id="8dbc0-104">The <xref:System.Printing.IndexedProperties> namespace provides a means to getting this information with using reflection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8dbc0-105">Пример</span><span class="sxs-lookup"><span data-stu-id="8dbc0-105">Example</span></span>  
 <span data-ttu-id="8dbc0-106">Ниже приведены действия по созданию.</span><span class="sxs-lookup"><span data-stu-id="8dbc0-106">The steps for doing this are as follows.</span></span>  
  
1.  <span data-ttu-id="8dbc0-107">Создайте экземпляр типа.</span><span class="sxs-lookup"><span data-stu-id="8dbc0-107">Create an instance of the type.</span></span> <span data-ttu-id="8dbc0-108">В следующем примере тип — <xref:System.Printing.PrintQueue> подойдет тип, который поставляется вместе с Microsoft .NET Framework, но код почти те же типы, производные от <xref:System.Printing.PrintSystemObject>.</span><span class="sxs-lookup"><span data-stu-id="8dbc0-108">In the example below, the type is the <xref:System.Printing.PrintQueue> type that ships with Microsoft .NET Framework, but nearly identical code should work for types that you derive from <xref:System.Printing.PrintSystemObject>.</span></span>  
  
2.  <span data-ttu-id="8dbc0-109">Создание <xref:System.Printing.IndexedProperties.PrintPropertyDictionary> по типу <xref:System.Printing.PrintSystemObject.PropertiesCollection%2A>.</span><span class="sxs-lookup"><span data-stu-id="8dbc0-109">Create a <xref:System.Printing.IndexedProperties.PrintPropertyDictionary> from the type's <xref:System.Printing.PrintSystemObject.PropertiesCollection%2A>.</span></span> <span data-ttu-id="8dbc0-110"><xref:System.Collections.DictionaryEntry.Value%2A> Каждой записи в этом словаре является объектом одного из типов, производных от <xref:System.Printing.IndexedProperties.PrintProperty>.</span><span class="sxs-lookup"><span data-stu-id="8dbc0-110">The <xref:System.Collections.DictionaryEntry.Value%2A> property of each entry in this dictionary is an object of one of the types derived from <xref:System.Printing.IndexedProperties.PrintProperty>.</span></span>  
  
3.  <span data-ttu-id="8dbc0-111">Перечислять элементы словаря.</span><span class="sxs-lookup"><span data-stu-id="8dbc0-111">Enumerate the members of the dictionary.</span></span> <span data-ttu-id="8dbc0-112">Для каждого из них выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="8dbc0-112">For each of them, do the following.</span></span>  
  
4.  <span data-ttu-id="8dbc0-113">Приведите значение каждого элемента в <xref:System.Printing.IndexedProperties.PrintProperty> и использовать его для создания <xref:System.Printing.IndexedProperties.PrintProperty> объекта.</span><span class="sxs-lookup"><span data-stu-id="8dbc0-113">Up-cast the value of each entry to <xref:System.Printing.IndexedProperties.PrintProperty> and use it to create a <xref:System.Printing.IndexedProperties.PrintProperty> object.</span></span>  
  
5.  <span data-ttu-id="8dbc0-114">Получить тип <xref:System.Printing.IndexedProperties.PrintProperty.Value%2A> каждого из <xref:System.Printing.IndexedProperties.PrintProperty> объекта.</span><span class="sxs-lookup"><span data-stu-id="8dbc0-114">Get the type of the <xref:System.Printing.IndexedProperties.PrintProperty.Value%2A> of each of the <xref:System.Printing.IndexedProperties.PrintProperty> object.</span></span>  
  
 [!code-csharp[GetPrintObjectPropertyTypesWithoutReflection#ShowPropertyTypesWithoutReflection](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GetPrintObjectPropertyTypesWithoutReflection/CSharp/Program.cs#showpropertytypeswithoutreflection)]
 [!code-vb[GetPrintObjectPropertyTypesWithoutReflection#ShowPropertyTypesWithoutReflection](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GetPrintObjectPropertyTypesWithoutReflection/visualbasic/program.vb#showpropertytypeswithoutreflection)]  
  
## <a name="see-also"></a><span data-ttu-id="8dbc0-115">См. также</span><span class="sxs-lookup"><span data-stu-id="8dbc0-115">See Also</span></span>  
 <xref:System.Printing.IndexedProperties.PrintProperty>  
 <xref:System.Printing.PrintSystemObject>  
 <xref:System.Printing.IndexedProperties>  
 <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>  
 <xref:System.Printing.LocalPrintServer>  
 <xref:System.Printing.PrintQueue>  
 <xref:System.Collections.DictionaryEntry>  
 [<span data-ttu-id="8dbc0-116">Документы в WPF</span><span class="sxs-lookup"><span data-stu-id="8dbc0-116">Documents in WPF</span></span>](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [<span data-ttu-id="8dbc0-117">Общие сведения о печати</span><span class="sxs-lookup"><span data-stu-id="8dbc0-117">Printing Overview</span></span>](../../../../docs/framework/wpf/advanced/printing-overview.md)
