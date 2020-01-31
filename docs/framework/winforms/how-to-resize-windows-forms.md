---
title: Изменить размер формы
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- resizing Windows Forms
- Windows Forms, resizing
ms.assetid: 5d9dd47e-e68c-48c9-a0a3-a9ff34ba009d
ms.openlocfilehash: 8d4ce46ada505f952fc3090d10c5d893338d19f2
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739305"
---
# <a name="how-to-resize-windows-forms"></a><span data-ttu-id="30ed2-102">Практическое руководство. Изменение размера формы в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="30ed2-102">How to: Resize Windows Forms</span></span>

<span data-ttu-id="30ed2-103">Размер формы Windows Forms можно указать несколькими способами.</span><span class="sxs-lookup"><span data-stu-id="30ed2-103">You can specify the size of your Windows Form in several ways.</span></span> <span data-ttu-id="30ed2-104">Вы можете изменить высоту и ширину формы программными средствами, задав новое значение для свойства <xref:System.Windows.Forms.Form.Size%2A> или изменив свойства <xref:System.Windows.Forms.Control.Height%2A> или <xref:System.Windows.Forms.Control.Width%2A> по отдельности.</span><span class="sxs-lookup"><span data-stu-id="30ed2-104">You can change both the height and the width of the form programmatically by setting a new value for the <xref:System.Windows.Forms.Form.Size%2A> property, or adjust the <xref:System.Windows.Forms.Control.Height%2A> or <xref:System.Windows.Forms.Control.Width%2A> properties individually.</span></span> <span data-ttu-id="30ed2-105">Если вы используете Visual Studio, можно изменить размер с помощью конструктор Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="30ed2-105">If you're using Visual Studio, you can change the size using the Windows Forms Designer.</span></span> <span data-ttu-id="30ed2-106">См. также [руководство. изменение размера Windows Forms с помощью конструктора](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/37k2zkwx(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="30ed2-106">Also see [How to: Resize Windows Forms Using the Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/37k2zkwx(v=vs.100)).</span></span>

## <a name="resize-a-form-programmatically"></a><span data-ttu-id="30ed2-107">Программное изменение размера формы</span><span class="sxs-lookup"><span data-stu-id="30ed2-107">Resize a form programmatically</span></span>

<span data-ttu-id="30ed2-108">Чтобы определить размер формы во время выполнения, задайте свойство <xref:System.Windows.Forms.Form.Size%2A> формы.</span><span class="sxs-lookup"><span data-stu-id="30ed2-108">Define the size of a form at run time by setting the <xref:System.Windows.Forms.Form.Size%2A> property of the form.</span></span>

<span data-ttu-id="30ed2-109">В примере кода ниже размер формы устанавливается равным 100 × 100 пикселей.</span><span class="sxs-lookup"><span data-stu-id="30ed2-109">The following code example shows the form size set to 100 × 100 pixels.</span></span>

```vb
Form1.Size = New System.Drawing.Size(100, 100)
```

```csharp
Form1.Size = new System.Drawing.Size(100, 100);
```

```cpp
Form1->Size = System::Drawing::Size(100, 100);
```

## <a name="change-form-width-and-height-programmatically"></a><span data-ttu-id="30ed2-110">Программное изменение ширины и высоты формы</span><span class="sxs-lookup"><span data-stu-id="30ed2-110">Change form width and height programmatically</span></span>

<span data-ttu-id="30ed2-111">Определив свойство <xref:System.Windows.Forms.Form.Size%2A>, измените высоту или ширину формы с помощью свойств <xref:System.Windows.Forms.Control.Width%2A> или <xref:System.Windows.Forms.Control.Height%2A>.</span><span class="sxs-lookup"><span data-stu-id="30ed2-111">After the <xref:System.Windows.Forms.Form.Size%2A> is defined, change either the form height or width by using the <xref:System.Windows.Forms.Control.Width%2A> or <xref:System.Windows.Forms.Control.Height%2A> properties.</span></span>

<span data-ttu-id="30ed2-112">В примере кода ниже для ширины формы устанавливается значение 300 пикселей, отсчитываемое от левого края формы. Высота остается неизменной.</span><span class="sxs-lookup"><span data-stu-id="30ed2-112">The following code example shows the width of the form set to 300 pixels from the left edge of the form, whereas the height stays constant.</span></span>

```vb
Form1.Width = 300
```

```csharp
Form1.Width = 300;
```

```cpp
Form1->Width = 300;
```

<span data-ttu-id="30ed2-113">\- или -</span><span class="sxs-lookup"><span data-stu-id="30ed2-113">-or-</span></span>

<span data-ttu-id="30ed2-114">Измените <xref:System.Drawing.Size.Width%2A> или <xref:System.Drawing.Size.Height%2A>, задав свойство <xref:System.Windows.Forms.Form.Size%2A>.</span><span class="sxs-lookup"><span data-stu-id="30ed2-114">Change <xref:System.Drawing.Size.Width%2A> or <xref:System.Drawing.Size.Height%2A> by setting the <xref:System.Windows.Forms.Form.Size%2A> property.</span></span>

<span data-ttu-id="30ed2-115">Однако в примере ниже показано, что этот подход является более громоздким, чем просто задание свойств <xref:System.Windows.Forms.Control.Width%2A> или <xref:System.Windows.Forms.Control.Height%2A>.</span><span class="sxs-lookup"><span data-stu-id="30ed2-115">However, as the following code example shows, this approach is more cumbersome than just setting <xref:System.Windows.Forms.Control.Width%2A> or <xref:System.Windows.Forms.Control.Height%2A> properties.</span></span>

```vb
Form1.Size = New Size(300, Form1.Size.Height)
```

```csharp
Form1.Size = new Size(300, Form1.Size.Height);
```

```cpp
Form1->Size = System::Drawing::Size(300, Form1->Size.Height);
```

## <a name="change-form-size-by-increments-programmatically"></a><span data-ttu-id="30ed2-116">Изменение размера формы с помощью приращений программными средствами</span><span class="sxs-lookup"><span data-stu-id="30ed2-116">Change form size by increments programmatically</span></span>

<span data-ttu-id="30ed2-117">Для увеличения размера формы задайте свойства <xref:System.Drawing.Size.Width%2A> или <xref:System.Drawing.Size.Height%2A>.</span><span class="sxs-lookup"><span data-stu-id="30ed2-117">To increment the size of the form, set the <xref:System.Drawing.Size.Width%2A> and <xref:System.Drawing.Size.Height%2A> properties.</span></span>

<span data-ttu-id="30ed2-118">В примере ниже ширина формы увеличивается на 200 пикселей по сравнению с первоначальным значением.</span><span class="sxs-lookup"><span data-stu-id="30ed2-118">The following code example shows the width of the form set to 200 pixels wider than the current setting.</span></span>

```vb
Form1.Width += 200
```

```csharp
Form1.Width += 200;
```

```cpp
Form1->Width += 200;
```

> [!CAUTION]
> <span data-ttu-id="30ed2-119">Всегда используйте свойство <xref:System.Drawing.Size.Height%2A> или <xref:System.Drawing.Size.Width%2A> для изменения размеров формы, если вы не устанавливаете значения высоты и ширины одновременно, присваивая свойству <xref:System.Windows.Forms.Form.Size%2A> новую структуру <xref:System.Drawing.Size>.</span><span class="sxs-lookup"><span data-stu-id="30ed2-119">Always use the <xref:System.Drawing.Size.Height%2A> or <xref:System.Drawing.Size.Width%2A> property to change a dimension of a form, unless you are setting both height and width dimensions at the same time by setting the <xref:System.Windows.Forms.Form.Size%2A> property to a new <xref:System.Drawing.Size> structure.</span></span> <span data-ttu-id="30ed2-120">Свойство <xref:System.Windows.Forms.Form.Size%2A> возвращает структуру <xref:System.Drawing.Size>, которая является типом значения.</span><span class="sxs-lookup"><span data-stu-id="30ed2-120">The <xref:System.Windows.Forms.Form.Size%2A> property returns a <xref:System.Drawing.Size> structure, which is a value type.</span></span> <span data-ttu-id="30ed2-121">Присвоить новое значение свойству типа значения нельзя.</span><span class="sxs-lookup"><span data-stu-id="30ed2-121">You cannot assign a new value to the property of a value type.</span></span> <span data-ttu-id="30ed2-122">Поэтому приведенный ниже пример кода компилироваться не будет.</span><span class="sxs-lookup"><span data-stu-id="30ed2-122">Therefore, the following code example will not compile.</span></span>

```vb
' NOTE: CODE WILL NOT COMPILE
Dim f As New Form()
f.Size.Width += 100
```

```csharp
// NOTE: CODE WILL NOT COMPILE
Form f = new Form();
f.Size.Width += 100;
```

```cpp
// NOTE: CODE WILL NOT COMPILE
Form^ f = gcnew Form();
f->Size->X += 100;
```

## <a name="see-also"></a><span data-ttu-id="30ed2-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="30ed2-123">See also</span></span>

- [<span data-ttu-id="30ed2-124">Приступая к работе с Windows Forms</span><span class="sxs-lookup"><span data-stu-id="30ed2-124">Getting Started with Windows Forms</span></span>](getting-started-with-windows-forms.md)
- [<span data-ttu-id="30ed2-125">Усовершенствование приложений Windows Forms</span><span class="sxs-lookup"><span data-stu-id="30ed2-125">Enhancing Windows Forms Applications</span></span>](./advanced/index.md)
