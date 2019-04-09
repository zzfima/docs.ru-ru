---
title: Практическое руководство. Извлечение данных в определенном формате данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drag-and-drop [WPF], retrieving data
- DataFormats class [WPF], retrieving data
- DataObject class [WPF], retrieving data
ms.assetid: a625acf3-1144-44cd-add7-456aefc3859f
ms.openlocfilehash: b3ec1b8fa873fd449956912e9e77e98b0362cb0e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59080024"
---
# <a name="how-to-retrieve-data-in-a-particular-data-format"></a><span data-ttu-id="d0b59-102">Практическое руководство. Извлечение данных в определенном формате данных</span><span class="sxs-lookup"><span data-stu-id="d0b59-102">How to: Retrieve Data in a Particular Data Format</span></span>
<span data-ttu-id="d0b59-103">В следующих примерах демонстрируется извлечение данных из объекта данных в указанном формате.</span><span class="sxs-lookup"><span data-stu-id="d0b59-103">The following examples show how to retrieve data from a data object in a specified format.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d0b59-104">Пример</span><span class="sxs-lookup"><span data-stu-id="d0b59-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="d0b59-105">Описание</span><span class="sxs-lookup"><span data-stu-id="d0b59-105">Description</span></span>  
 <span data-ttu-id="d0b59-106">В следующем примере кода используется <xref:System.Windows.DataObject.GetDataPresent%28System.String%29> перегрузки для первоначальной проверки, если формат указанных данных доступен (в собственном коде или с автоматическим преобразованием); Если доступен указанный формат, данные извлекаются с помощью <xref:System.Windows.DataObject.GetData%28System.String%29> метод.</span><span class="sxs-lookup"><span data-stu-id="d0b59-106">The following example code uses the <xref:System.Windows.DataObject.GetDataPresent%28System.String%29> overload to first check if a specified data format is available (natively or by auto-convert); if the specified format is available, the example retrieves the data by using the <xref:System.Windows.DataObject.GetData%28System.String%29> method.</span></span>  
  
### <a name="code"></a><span data-ttu-id="d0b59-107">Код</span><span class="sxs-lookup"><span data-stu-id="d0b59-107">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getspecificdataformat)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getspecificdataformat)]  
  
## <a name="example"></a><span data-ttu-id="d0b59-108">Пример</span><span class="sxs-lookup"><span data-stu-id="d0b59-108">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="d0b59-109">Описание</span><span class="sxs-lookup"><span data-stu-id="d0b59-109">Description</span></span>  
 <span data-ttu-id="d0b59-110">В следующем примере кода используется <xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29> перегрузку нужно сначала проверки заданного формата данных в собственном коде (фильтруются автоматически преобразуемые форматы); Если доступен указанный формат, данные извлекаются с помощью <xref:System.Windows.DataObject.GetData%28System.String%29>метод.</span><span class="sxs-lookup"><span data-stu-id="d0b59-110">The following example code uses the <xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29> overload to first check if a specified data format is available natively (auto-convertible data formats are filtered); if the specified format is available, the example retrieves the data by using the <xref:System.Windows.DataObject.GetData%28System.String%29> method.</span></span>  
  
### <a name="code"></a><span data-ttu-id="d0b59-111">Код</span><span class="sxs-lookup"><span data-stu-id="d0b59-111">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat_Native](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getspecificdataformat_native)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat_Native](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getspecificdataformat_native)]  
  
## <a name="see-also"></a><span data-ttu-id="d0b59-112">См. также</span><span class="sxs-lookup"><span data-stu-id="d0b59-112">See also</span></span>

- <xref:System.Windows.IDataObject>
- [<span data-ttu-id="d0b59-113">Общие сведения о перетаскивании</span><span class="sxs-lookup"><span data-stu-id="d0b59-113">Drag and Drop Overview</span></span>](drag-and-drop-overview.md)
