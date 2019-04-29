---
title: Практическое руководство. Определение присутствия формата данных в объекте данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataFormats class [WPF]
- drag-and-drop [WPF], data formats present
- data formats [WPF], determining if present
ms.assetid: e487a454-c9fc-4e53-aeaa-c458d059ad4c
ms.openlocfilehash: 4cec733490e2a9dc5d54b3b253ac38a5090ac885
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61776250"
---
# <a name="how-to-determine-if-a-data-format-is-present-in-a-data-object"></a><span data-ttu-id="af11b-102">Практическое руководство. Определение присутствия формата данных в объекте данных</span><span class="sxs-lookup"><span data-stu-id="af11b-102">How to: Determine if a Data Format is Present in a Data Object</span></span>
<span data-ttu-id="af11b-103">Следующие примеры показывают, как использовать различные <xref:System.Windows.DataObject.GetDataPresent%2A> перегрузки метода к запросу ли определенного формата данных присутствует в объекте данных.</span><span class="sxs-lookup"><span data-stu-id="af11b-103">The following examples show how to use the various <xref:System.Windows.DataObject.GetDataPresent%2A> method overloads to query whether a particular data format is present in a data object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="af11b-104">Пример</span><span class="sxs-lookup"><span data-stu-id="af11b-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="af11b-105">Описание</span><span class="sxs-lookup"><span data-stu-id="af11b-105">Description</span></span>  
 <span data-ttu-id="af11b-106">В следующем примере кода используется <xref:System.Windows.DataObject.GetDataPresent%28System.String%29> перегрузки для запроса на наличие определенного формата данных, строки дескриптора.</span><span class="sxs-lookup"><span data-stu-id="af11b-106">The following example code uses the <xref:System.Windows.DataObject.GetDataPresent%28System.String%29> overload to query for the presence of a particular data format by descriptor string.</span></span>  
  
### <a name="code"></a><span data-ttu-id="af11b-107">Код</span><span class="sxs-lookup"><span data-stu-id="af11b-107">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_String](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_querydataformats_string)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_String](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_querydataformats_string)]  
  
## <a name="example"></a><span data-ttu-id="af11b-108">Пример</span><span class="sxs-lookup"><span data-stu-id="af11b-108">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="af11b-109">Описание</span><span class="sxs-lookup"><span data-stu-id="af11b-109">Description</span></span>  
 <span data-ttu-id="af11b-110">В следующем примере кода используется <xref:System.Windows.DataObject.GetDataPresent%28System.Type%29> перегрузки для запроса на наличие определенного формата данных по типу.</span><span class="sxs-lookup"><span data-stu-id="af11b-110">The following example code uses the <xref:System.Windows.DataObject.GetDataPresent%28System.Type%29> overload to query for the presence of a particular data format by type.</span></span>  
  
### <a name="code"></a><span data-ttu-id="af11b-111">Код</span><span class="sxs-lookup"><span data-stu-id="af11b-111">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_Type](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_querydataformats_type)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_Type](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_querydataformats_type)]  
  
## <a name="example"></a><span data-ttu-id="af11b-112">Пример</span><span class="sxs-lookup"><span data-stu-id="af11b-112">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="af11b-113">Описание</span><span class="sxs-lookup"><span data-stu-id="af11b-113">Description</span></span>  
 <span data-ttu-id="af11b-114">В следующем примере кода используется <xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29> перегрузки для запроса к данным по строке дескриптора и указать способ обрабатывать форматы автоматически преобразуемые данные.</span><span class="sxs-lookup"><span data-stu-id="af11b-114">The following example code uses the <xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29> overload to query for data by descriptor string, and specifying how to treat auto-convertible data formats.</span></span>  
  
### <a name="code"></a><span data-ttu-id="af11b-115">Код</span><span class="sxs-lookup"><span data-stu-id="af11b-115">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_Autoconvert](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_querydataformats_autoconvert)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_Autoconvert](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_querydataformats_autoconvert)]  
  
## <a name="see-also"></a><span data-ttu-id="af11b-116">См. также</span><span class="sxs-lookup"><span data-stu-id="af11b-116">See also</span></span>

- <xref:System.Windows.IDataObject>
