---
title: Практическое руководство. Создание кнопки, содержащей изображение
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Button controls [WPF], creating
ms.assetid: 607a193c-4098-4dd8-8dc0-51256cec2020
ms.openlocfilehash: 9fb871aa39461329654c0289f00bd3080a633913
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33550944"
---
# <a name="how-to-create-a-button-that-has-an-image"></a><span data-ttu-id="fa6a7-102">Практическое руководство. Создание кнопки, содержащей изображение</span><span class="sxs-lookup"><span data-stu-id="fa6a7-102">How to: Create a Button That Has an Image</span></span>
<span data-ttu-id="fa6a7-103">В этом примере показано, как включить изображение в <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="fa6a7-103">This example shows how to include an image on a <xref:System.Windows.Controls.Button>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fa6a7-104">Пример</span><span class="sxs-lookup"><span data-stu-id="fa6a7-104">Example</span></span>  
 <span data-ttu-id="fa6a7-105">В следующем примере создается два <xref:System.Windows.Controls.Button> элементов управления.</span><span class="sxs-lookup"><span data-stu-id="fa6a7-105">The following example creates two <xref:System.Windows.Controls.Button> controls.</span></span> <span data-ttu-id="fa6a7-106">Один <xref:System.Windows.Controls.Button> содержит текст, а другой изображения.</span><span class="sxs-lookup"><span data-stu-id="fa6a7-106">One <xref:System.Windows.Controls.Button> contains text and the other contains an image.</span></span> <span data-ttu-id="fa6a7-107">Изображение находится в папке Data, которая вложена в папку проекта этого примера.</span><span class="sxs-lookup"><span data-stu-id="fa6a7-107">The image is in a folder called data, which is a subfolder of the example’s project folder.</span></span> <span data-ttu-id="fa6a7-108">Когда пользователь щелкает <xref:System.Windows.Controls.Button> , содержащее изображения, фон и текст другого <xref:System.Windows.Controls.Button> изменения.</span><span class="sxs-lookup"><span data-stu-id="fa6a7-108">When a user clicks the <xref:System.Windows.Controls.Button> that has the image, the background and the text of the other <xref:System.Windows.Controls.Button> change.</span></span>  
  
 <span data-ttu-id="fa6a7-109">В этом примере создается <xref:System.Windows.Controls.Button> элементы управления с помощью разметки, но использует код, записываемый <xref:System.Windows.Controls.Primitives.ButtonBase.Click> обработчики событий.</span><span class="sxs-lookup"><span data-stu-id="fa6a7-109">This example creates <xref:System.Windows.Controls.Button> controls by using markup but uses code to write the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handlers.</span></span>  
  
 [!code-xaml[BtnColor#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BtnColor/CSharp/Pane1.xaml#4)]  
  
 [!code-csharp[BtnColor#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BtnColor/CSharp/Pane1.xaml.cs#6)]
 [!code-vb[BtnColor#6](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BtnColor/VisualBasic/Pane1.xaml.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="fa6a7-110">См. также</span><span class="sxs-lookup"><span data-stu-id="fa6a7-110">See Also</span></span>  
 [<span data-ttu-id="fa6a7-111">Элементы управления</span><span class="sxs-lookup"><span data-stu-id="fa6a7-111">Controls</span></span>](../../../../docs/framework/wpf/controls/index.md)  
 [<span data-ttu-id="fa6a7-112">Библиотека элементов управления</span><span class="sxs-lookup"><span data-stu-id="fa6a7-112">Control Library</span></span>](../../../../docs/framework/wpf/controls/control-library.md)
