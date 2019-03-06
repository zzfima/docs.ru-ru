---
title: Практическое руководство. Создание кнопки, содержащей изображение
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Button controls [WPF], creating
ms.assetid: 607a193c-4098-4dd8-8dc0-51256cec2020
ms.openlocfilehash: fe9f35a6f83c5a839823d94c4d3c55e01b192fb1
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57352039"
---
# <a name="how-to-create-a-button-that-has-an-image"></a><span data-ttu-id="dd5bb-102">Практическое руководство. Создание кнопки, содержащей изображение</span><span class="sxs-lookup"><span data-stu-id="dd5bb-102">How to: Create a Button That Has an Image</span></span>
<span data-ttu-id="dd5bb-103">В этом примере показано, как включить изображение в <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="dd5bb-103">This example shows how to include an image on a <xref:System.Windows.Controls.Button>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dd5bb-104">Пример</span><span class="sxs-lookup"><span data-stu-id="dd5bb-104">Example</span></span>  
 <span data-ttu-id="dd5bb-105">В следующем примере создается два <xref:System.Windows.Controls.Button> элементов управления.</span><span class="sxs-lookup"><span data-stu-id="dd5bb-105">The following example creates two <xref:System.Windows.Controls.Button> controls.</span></span> <span data-ttu-id="dd5bb-106">Один <xref:System.Windows.Controls.Button> содержит текст, а другой образ.</span><span class="sxs-lookup"><span data-stu-id="dd5bb-106">One <xref:System.Windows.Controls.Button> contains text and the other contains an image.</span></span> <span data-ttu-id="dd5bb-107">Изображение находится в папке Data, которая является подпапкой папки проекта в примере.</span><span class="sxs-lookup"><span data-stu-id="dd5bb-107">The image is in a folder called data, which is a subfolder of the example’s project folder.</span></span> <span data-ttu-id="dd5bb-108">Когда пользователь щелкает <xref:System.Windows.Controls.Button> имеет изображения, фон и текст другого <xref:System.Windows.Controls.Button> изменить.</span><span class="sxs-lookup"><span data-stu-id="dd5bb-108">When a user clicks the <xref:System.Windows.Controls.Button> that has the image, the background and the text of the other <xref:System.Windows.Controls.Button> change.</span></span>  
  
 <span data-ttu-id="dd5bb-109">В этом примере создается <xref:System.Windows.Controls.Button> элементы управления с помощью разметки, но использует код для записи <xref:System.Windows.Controls.Primitives.ButtonBase.Click> обработчики событий.</span><span class="sxs-lookup"><span data-stu-id="dd5bb-109">This example creates <xref:System.Windows.Controls.Button> controls by using markup but uses code to write the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handlers.</span></span>  
  
 [!code-xaml[BtnColor#4](~/samples/snippets/csharp/VS_Snippets_Wpf/BtnColor/CSharp/Pane1.xaml#4)]  
  
 [!code-csharp[BtnColor#6](~/samples/snippets/csharp/VS_Snippets_Wpf/BtnColor/CSharp/Pane1.xaml.cs#6)]
 [!code-vb[BtnColor#6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BtnColor/VisualBasic/Pane1.xaml.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="dd5bb-110">См. также</span><span class="sxs-lookup"><span data-stu-id="dd5bb-110">See also</span></span>
- [<span data-ttu-id="dd5bb-111">Элементы управления</span><span class="sxs-lookup"><span data-stu-id="dd5bb-111">Controls</span></span>](index.md)
- [<span data-ttu-id="dd5bb-112">Библиотека элементов управления</span><span class="sxs-lookup"><span data-stu-id="dd5bb-112">Control Library</span></span>](control-library.md)
