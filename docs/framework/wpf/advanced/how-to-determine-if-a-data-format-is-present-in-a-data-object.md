---
title: "Практическое руководство. Определение присутствия формата данных в объекте данных"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataFormats class [WPF]
- drag-and-drop [WPF], data formats present
- data formats [WPF], determining if present
ms.assetid: e487a454-c9fc-4e53-aeaa-c458d059ad4c
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fb7b7bb0436ad00982f48a00b079e1f867922db5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-determine-if-a-data-format-is-present-in-a-data-object"></a><span data-ttu-id="aae59-102">Практическое руководство. Определение присутствия формата данных в объекте данных</span><span class="sxs-lookup"><span data-stu-id="aae59-102">How to: Determine if a Data Format is Present in a Data Object</span></span>
<span data-ttu-id="aae59-103">Следующие примеры показывают, как использовать различные <xref:System.Windows.DataObject.GetDataPresent%2A> запрос перегрузки метода, определенного формата данных существует ли в объект данных.</span><span class="sxs-lookup"><span data-stu-id="aae59-103">The following examples show how to use the various <xref:System.Windows.DataObject.GetDataPresent%2A> method overloads to query whether a particular data format is present in a data object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aae59-104">Пример</span><span class="sxs-lookup"><span data-stu-id="aae59-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="aae59-105">Описание:</span><span class="sxs-lookup"><span data-stu-id="aae59-105">Description</span></span>  
 <span data-ttu-id="aae59-106">В следующем примере кода используется <xref:System.Windows.DataObject.GetDataPresent%28System.String%29> перегрузка для запроса на наличие определенного формата данных по строке дескриптора.</span><span class="sxs-lookup"><span data-stu-id="aae59-106">The following example code uses the <xref:System.Windows.DataObject.GetDataPresent%28System.String%29> overload to query for the presence of a particular data format by descriptor string.</span></span>  
  
### <a name="code"></a><span data-ttu-id="aae59-107">Код</span><span class="sxs-lookup"><span data-stu-id="aae59-107">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_String](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_querydataformats_string)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_String](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_querydataformats_string)]  
  
## <a name="example"></a><span data-ttu-id="aae59-108">Пример</span><span class="sxs-lookup"><span data-stu-id="aae59-108">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="aae59-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="aae59-109">Description</span></span>  
 <span data-ttu-id="aae59-110">В следующем примере кода используется <xref:System.Windows.DataObject.GetDataPresent%28System.Type%29> перегрузка для запроса на наличие определенного формата данных по типу.</span><span class="sxs-lookup"><span data-stu-id="aae59-110">The following example code uses the <xref:System.Windows.DataObject.GetDataPresent%28System.Type%29> overload to query for the presence of a particular data format by type.</span></span>  
  
### <a name="code"></a><span data-ttu-id="aae59-111">Код</span><span class="sxs-lookup"><span data-stu-id="aae59-111">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_Type](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_querydataformats_type)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_Type](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_querydataformats_type)]  
  
## <a name="example"></a><span data-ttu-id="aae59-112">Пример</span><span class="sxs-lookup"><span data-stu-id="aae59-112">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="aae59-113">Описание:</span><span class="sxs-lookup"><span data-stu-id="aae59-113">Description</span></span>  
 <span data-ttu-id="aae59-114">В следующем примере кода используется <xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29> перегрузки для запроса к данным по строке дескриптора и указание того, как обрабатывать автоматически преобразуемые форматы данных.</span><span class="sxs-lookup"><span data-stu-id="aae59-114">The following example code uses the <xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29> overload to query for data by descriptor string, and specifying how to treat auto-convertible data formats.</span></span>  
  
### <a name="code"></a><span data-ttu-id="aae59-115">Код</span><span class="sxs-lookup"><span data-stu-id="aae59-115">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_Autoconvert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_querydataformats_autoconvert)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_Autoconvert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_querydataformats_autoconvert)]  
  
## <a name="see-also"></a><span data-ttu-id="aae59-116">См. также</span><span class="sxs-lookup"><span data-stu-id="aae59-116">See Also</span></span>  
 <xref:System.Windows.IDataObject>
