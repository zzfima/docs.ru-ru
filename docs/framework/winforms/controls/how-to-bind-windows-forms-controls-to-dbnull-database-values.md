---
title: Привязка элементов управления к значениям базы данных DBNull
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- BindingSource component [Windows Forms], binding to DBNull values
- examples [Windows Forms], BindingSource component
- controls [Windows Forms], binding to DBNull values
ms.assetid: 96494e6f-5f40-4f83-af97-bbd7192c2af8
ms.openlocfilehash: 175d7f5aee2540916480e2c55a485af1f9d16653
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746665"
---
# <a name="how-to-bind-windows-forms-controls-to-dbnull-database-values"></a><span data-ttu-id="6d2d3-102">Практическое руководство. Специальная обработка значений DBNull при связывании элементов управления с данными в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6d2d3-102">How to: Bind Windows Forms Controls to DBNull Database Values</span></span>
<span data-ttu-id="6d2d3-103">Если элементы управления Windows Forms привязаны к источнику данных и источник данных возвращает значение <xref:System.DBNull>, соответствующее значение можно заменить без обработки, форматирования или анализа событий.</span><span class="sxs-lookup"><span data-stu-id="6d2d3-103">When you bind Windows Forms controls to a data source and the data source returns a <xref:System.DBNull> value, you can substitute an appropriate value without handling, formatting, or parsing events.</span></span> <span data-ttu-id="6d2d3-104">Свойство <xref:System.Windows.Forms.Binding.NullValue%2A> преобразует <xref:System.DBNull> в указанный объект при форматировании или анализе значений источника данных.</span><span class="sxs-lookup"><span data-stu-id="6d2d3-104">The <xref:System.Windows.Forms.Binding.NullValue%2A> property will convert <xref:System.DBNull> to a specified object when formatting or parsing the data source values.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6d2d3-105">Пример</span><span class="sxs-lookup"><span data-stu-id="6d2d3-105">Example</span></span>  
 <span data-ttu-id="6d2d3-106">В примере ниже демонстрируется привязка значения <xref:System.DBNull> в двух разных случаях.</span><span class="sxs-lookup"><span data-stu-id="6d2d3-106">The following example demonstrates how to bind a <xref:System.DBNull> value in two different situations.</span></span> <span data-ttu-id="6d2d3-107">В первом случае показано, как задать <xref:System.Windows.Forms.Binding.NullValue%2A> для свойства строки; во втором — как задать <xref:System.Windows.Forms.Binding.NullValue%2A> для свойства изображения.</span><span class="sxs-lookup"><span data-stu-id="6d2d3-107">The first demonstrates how to set the <xref:System.Windows.Forms.Binding.NullValue%2A> for a string property; the second demonstrates how to set the <xref:System.Windows.Forms.Binding.NullValue%2A> for an image property.</span></span>  
  
 [!code-csharp[System.Windows.Forms.BindingDBNull#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingDBNull/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.BindingDBNull#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingDBNull/VB/form1.vb#1)]  
  
 <span data-ttu-id="6d2d3-108">Типы связанного свойства и свойства <xref:System.Windows.Forms.Binding.NullValue%2A> должны быть одинаковыми, иначе произойдет ошибка и следующие значения <xref:System.Windows.Forms.Binding.NullValue%2A> обрабатываться не будут.</span><span class="sxs-lookup"><span data-stu-id="6d2d3-108">The types of the bound property and the <xref:System.Windows.Forms.Binding.NullValue%2A> property must be the same or an error will result, and no further <xref:System.Windows.Forms.Binding.NullValue%2A> values will be processed.</span></span> <span data-ttu-id="6d2d3-109">В этом случае исключение не создается.</span><span class="sxs-lookup"><span data-stu-id="6d2d3-109">In this situation, an exception will not be thrown.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="6d2d3-110">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="6d2d3-110">Compiling the Code</span></span>  
 <span data-ttu-id="6d2d3-111">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="6d2d3-111">This example requires:</span></span>  
  
- <span data-ttu-id="6d2d3-112">ссылки на сборки System, System.Data, System.Drawing и System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="6d2d3-112">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d2d3-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="6d2d3-113">See also</span></span>

- [<span data-ttu-id="6d2d3-114">Компонент BindingSource</span><span class="sxs-lookup"><span data-stu-id="6d2d3-114">BindingSource Component</span></span>](bindingsource-component.md)
- [<span data-ttu-id="6d2d3-115">Практическое руководство. Обработка ошибок и исключений, происходящих при связывании элементов управления с данными</span><span class="sxs-lookup"><span data-stu-id="6d2d3-115">How to: Handle Errors and Exceptions that Occur with Databinding</span></span>](how-to-handle-errors-and-exceptions-that-occur-with-databinding.md)
- [<span data-ttu-id="6d2d3-116">Практическое руководство. Связывание элемента управления с типом в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6d2d3-116">How to: Bind a Windows Forms Control to a Type</span></span>](how-to-bind-a-windows-forms-control-to-a-type.md)
