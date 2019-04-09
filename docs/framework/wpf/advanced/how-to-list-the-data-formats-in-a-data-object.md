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
ms.openlocfilehash: f8230eac33a18a0d99cc757d54c2b901c1afe977
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59077749"
---
# <a name="how-to-list-the-data-formats-in-a-data-object"></a><span data-ttu-id="c9d75-102">Практическое руководство. Перечисление форматов данных в объекте данных</span><span class="sxs-lookup"><span data-stu-id="c9d75-102">How to: List the Data Formats in a Data Object</span></span>
<span data-ttu-id="c9d75-103">Следующие примеры показывают, как использовать <xref:System.Windows.DataObject.GetFormats%2A> перегрузок метода получить массив строк, обозначающих каждого формата данных, который доступен в объекте данных.</span><span class="sxs-lookup"><span data-stu-id="c9d75-103">The following examples show how to use the <xref:System.Windows.DataObject.GetFormats%2A> method overloads get an array of strings denoting each data format that is available in a data object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c9d75-104">Пример</span><span class="sxs-lookup"><span data-stu-id="c9d75-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="c9d75-105">Описание</span><span class="sxs-lookup"><span data-stu-id="c9d75-105">Description</span></span>  
 <span data-ttu-id="c9d75-106">В следующем примере кода используется <xref:System.Windows.DataObject.GetFormats%2A> перегрузки, чтобы получить массив строк, обозначающих все форматы данных, доступные в объекте данных (как собственные, так и автоматически преобразуемые).</span><span class="sxs-lookup"><span data-stu-id="c9d75-106">The following example code uses the <xref:System.Windows.DataObject.GetFormats%2A> overload to get an array of strings denoting all data formats available in a data object (both native and auto-convertible).</span></span>  
  
### <a name="code"></a><span data-ttu-id="c9d75-107">Код</span><span class="sxs-lookup"><span data-stu-id="c9d75-107">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getalldataformats)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getalldataformats)]  
  
## <a name="example"></a><span data-ttu-id="c9d75-108">Пример</span><span class="sxs-lookup"><span data-stu-id="c9d75-108">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="c9d75-109">Описание</span><span class="sxs-lookup"><span data-stu-id="c9d75-109">Description</span></span>  
 <span data-ttu-id="c9d75-110">В следующем примере кода используется <xref:System.Windows.DataObject.GetFormats%2A> перегрузку для получения массива строк, обозначающих только форматы данных, доступных в объекте данных (автоматически преобразуемые данные фильтруются форматы).</span><span class="sxs-lookup"><span data-stu-id="c9d75-110">The following example code uses the <xref:System.Windows.DataObject.GetFormats%2A> overload to get an array of strings denoting only data formats available in a data object (auto-convertible data formats are filtered).</span></span>  
  
### <a name="code"></a><span data-ttu-id="c9d75-111">Код</span><span class="sxs-lookup"><span data-stu-id="c9d75-111">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats_NativeOnly](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getalldataformats_nativeonly)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats_NativeOnly](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getalldataformats_nativeonly)]  
  
## <a name="see-also"></a><span data-ttu-id="c9d75-112">См. также</span><span class="sxs-lookup"><span data-stu-id="c9d75-112">See also</span></span>

- <xref:System.Windows.IDataObject>
- [<span data-ttu-id="c9d75-113">Общие сведения о перетаскивании</span><span class="sxs-lookup"><span data-stu-id="c9d75-113">Drag and Drop Overview</span></span>](drag-and-drop-overview.md)
