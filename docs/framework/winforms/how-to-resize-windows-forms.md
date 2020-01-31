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
# <a name="how-to-resize-windows-forms"></a>Практическое руководство. Изменение размера формы в Windows Forms

Размер формы Windows Forms можно указать несколькими способами. Вы можете изменить высоту и ширину формы программными средствами, задав новое значение для свойства <xref:System.Windows.Forms.Form.Size%2A> или изменив свойства <xref:System.Windows.Forms.Control.Height%2A> или <xref:System.Windows.Forms.Control.Width%2A> по отдельности. Если вы используете Visual Studio, можно изменить размер с помощью конструктор Windows Forms. См. также [руководство. изменение размера Windows Forms с помощью конструктора](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/37k2zkwx(v=vs.100)).

## <a name="resize-a-form-programmatically"></a>Программное изменение размера формы

Чтобы определить размер формы во время выполнения, задайте свойство <xref:System.Windows.Forms.Form.Size%2A> формы.

В примере кода ниже размер формы устанавливается равным 100 × 100 пикселей.

```vb
Form1.Size = New System.Drawing.Size(100, 100)
```

```csharp
Form1.Size = new System.Drawing.Size(100, 100);
```

```cpp
Form1->Size = System::Drawing::Size(100, 100);
```

## <a name="change-form-width-and-height-programmatically"></a>Программное изменение ширины и высоты формы

Определив свойство <xref:System.Windows.Forms.Form.Size%2A>, измените высоту или ширину формы с помощью свойств <xref:System.Windows.Forms.Control.Width%2A> или <xref:System.Windows.Forms.Control.Height%2A>.

В примере кода ниже для ширины формы устанавливается значение 300 пикселей, отсчитываемое от левого края формы. Высота остается неизменной.

```vb
Form1.Width = 300
```

```csharp
Form1.Width = 300;
```

```cpp
Form1->Width = 300;
```

\- или -

Измените <xref:System.Drawing.Size.Width%2A> или <xref:System.Drawing.Size.Height%2A>, задав свойство <xref:System.Windows.Forms.Form.Size%2A>.

Однако в примере ниже показано, что этот подход является более громоздким, чем просто задание свойств <xref:System.Windows.Forms.Control.Width%2A> или <xref:System.Windows.Forms.Control.Height%2A>.

```vb
Form1.Size = New Size(300, Form1.Size.Height)
```

```csharp
Form1.Size = new Size(300, Form1.Size.Height);
```

```cpp
Form1->Size = System::Drawing::Size(300, Form1->Size.Height);
```

## <a name="change-form-size-by-increments-programmatically"></a>Изменение размера формы с помощью приращений программными средствами

Для увеличения размера формы задайте свойства <xref:System.Drawing.Size.Width%2A> или <xref:System.Drawing.Size.Height%2A>.

В примере ниже ширина формы увеличивается на 200 пикселей по сравнению с первоначальным значением.

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
> Всегда используйте свойство <xref:System.Drawing.Size.Height%2A> или <xref:System.Drawing.Size.Width%2A> для изменения размеров формы, если вы не устанавливаете значения высоты и ширины одновременно, присваивая свойству <xref:System.Windows.Forms.Form.Size%2A> новую структуру <xref:System.Drawing.Size>. Свойство <xref:System.Windows.Forms.Form.Size%2A> возвращает структуру <xref:System.Drawing.Size>, которая является типом значения. Присвоить новое значение свойству типа значения нельзя. Поэтому приведенный ниже пример кода компилироваться не будет.

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

## <a name="see-also"></a>См. также:

- [Приступая к работе с Windows Forms](getting-started-with-windows-forms.md)
- [Усовершенствование приложений Windows Forms](./advanced/index.md)
