---
title: Практическое руководство. Перечисление форматов данных в объекте данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drag-and-drop [WPF], listing data formats
- DataFormats class [WPF]
- data formats [WPF], listing
ms.assetid: 18e7ba4b-ccef-4815-ae2d-3a32891010c0
ms.openlocfilehash: c0e5917d52d9253737a56307beed69bc0255807c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-list-the-data-formats-in-a-data-object"></a><span data-ttu-id="b2ca2-102">Практическое руководство. Перечисление форматов данных в объекте данных</span><span class="sxs-lookup"><span data-stu-id="b2ca2-102">How to: List the Data Formats in a Data Object</span></span>
<span data-ttu-id="b2ca2-103">В следующих примерах показано использование <xref:System.Windows.DataObject.GetFormats%2A> перегруженных версий метода для получения массива строк, обозначающих каждого формата данных, который доступен в объект данных.</span><span class="sxs-lookup"><span data-stu-id="b2ca2-103">The following examples show how to use the <xref:System.Windows.DataObject.GetFormats%2A> method overloads get an array of strings denoting each data format that is available in a data object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b2ca2-104">Пример</span><span class="sxs-lookup"><span data-stu-id="b2ca2-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="b2ca2-105">Описание</span><span class="sxs-lookup"><span data-stu-id="b2ca2-105">Description</span></span>  
 <span data-ttu-id="b2ca2-106">В следующем примере кода используется <xref:System.Windows.DataObject.GetFormats%2A> перегрузку, чтобы получить массив строк, обозначающих все форматы данных, доступные в объекте данных (собственный и автоматически преобразуемые).</span><span class="sxs-lookup"><span data-stu-id="b2ca2-106">The following example code uses the <xref:System.Windows.DataObject.GetFormats%2A> overload to get an array of strings denoting all data formats available in a data object (both native and auto-convertible).</span></span>  
  
### <a name="code"></a><span data-ttu-id="b2ca2-107">Код</span><span class="sxs-lookup"><span data-stu-id="b2ca2-107">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getalldataformats)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getalldataformats)]  
  
## <a name="example"></a><span data-ttu-id="b2ca2-108">Пример</span><span class="sxs-lookup"><span data-stu-id="b2ca2-108">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="b2ca2-109">Описание</span><span class="sxs-lookup"><span data-stu-id="b2ca2-109">Description</span></span>  
 <span data-ttu-id="b2ca2-110">В следующем примере кода используется <xref:System.Windows.DataObject.GetFormats%2A> перегрузку, чтобы получить массив строк, обозначающих только форматы данных, доступные в объекте данных (фильтруются форматы данных автоматически преобразуемые).</span><span class="sxs-lookup"><span data-stu-id="b2ca2-110">The following example code uses the <xref:System.Windows.DataObject.GetFormats%2A> overload to get an array of strings denoting only data formats available in a data object (auto-convertible data formats are filtered).</span></span>  
  
### <a name="code"></a><span data-ttu-id="b2ca2-111">Код</span><span class="sxs-lookup"><span data-stu-id="b2ca2-111">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats_NativeOnly](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getalldataformats_nativeonly)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats_NativeOnly](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getalldataformats_nativeonly)]  
  
## <a name="see-also"></a><span data-ttu-id="b2ca2-112">См. также</span><span class="sxs-lookup"><span data-stu-id="b2ca2-112">See Also</span></span>  
 <xref:System.Windows.IDataObject>  
 [<span data-ttu-id="b2ca2-113">Общие сведения о перетаскивании</span><span class="sxs-lookup"><span data-stu-id="b2ca2-113">Drag and Drop Overview</span></span>](../../../../docs/framework/wpf/advanced/drag-and-drop-overview.md)
