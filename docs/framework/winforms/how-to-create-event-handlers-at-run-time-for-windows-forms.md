---
title: Как создавать обработчики событий во время выполнения
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms, event handling
- event handlers [Windows Forms], creating
- run time [Windows Forms], creating event handlers at
- examples [Windows Forms], event handling
- Button control [Windows Forms], event handlers
ms.assetid: 2e7c9e1a-61fe-444d-8113-3c5bacf1c8cb
ms.openlocfilehash: 0b496a3da77c5bcf7a08c435edba468a7c5809cb
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739506"
---
# <a name="how-to-create-event-handlers-at-run-time-for-windows-forms"></a><span data-ttu-id="d4c9f-102">Практическое руководство. Создание обработчиков событий для Windows Forms во время выполнения</span><span class="sxs-lookup"><span data-stu-id="d4c9f-102">How to: Create Event Handlers at Run Time for Windows Forms</span></span>

<span data-ttu-id="d4c9f-103">Помимо создания событий с помощью конструктор Windows Forms в Visual Studio можно также создать обработчик событий во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="d4c9f-103">In addition to creating events using the Windows Forms Designer in Visual Studio, you can also create an event handler at run time.</span></span> <span data-ttu-id="d4c9f-104">Это позволит подключать обработчики событий в зависимости от условий в коде во время выполнения, а не при начальном запуске программы.</span><span class="sxs-lookup"><span data-stu-id="d4c9f-104">This action allows you to connect event handlers based on conditions in code at run time as opposed to having them connected when the program initially starts.</span></span>

## <a name="create-an-event-handler-at-run-time"></a><span data-ttu-id="d4c9f-105">Создание обработчика событий во время выполнения</span><span class="sxs-lookup"><span data-stu-id="d4c9f-105">Create an event handler at run time</span></span>

1. <span data-ttu-id="d4c9f-106">Откройте форму, в которую нужно добавить обработчик событий.</span><span class="sxs-lookup"><span data-stu-id="d4c9f-106">Open the form that you want to add an event handler to.</span></span>

2. <span data-ttu-id="d4c9f-107">Добавьте метод в форму с сигнатурой метода для события, которое будет необходимо обрабатывать.</span><span class="sxs-lookup"><span data-stu-id="d4c9f-107">Add a method to your form with the method signature for the event that you want to handle.</span></span>

     <span data-ttu-id="d4c9f-108">Например, при обработке события <xref:System.Windows.Forms.Control.Click> элемента управления <xref:System.Windows.Forms.Button> необходимо создать метод, подобный следующему:</span><span class="sxs-lookup"><span data-stu-id="d4c9f-108">For example, if you were handling the <xref:System.Windows.Forms.Control.Click> event of a <xref:System.Windows.Forms.Button> control, you would create a method such as the following:</span></span>

    ```vb
    Private Sub Button1_Click(ByVal sender As Object, ByVal e As EventArgs)
       ' Add event handler code here.
    End Sub
    ```

    ```csharp
    private void button1_Click(object sender, System.EventArgs e)
    {
    // Add event handler code here.
    }
    ```

    ```cpp
    private:
       void button1_Click(System::Object ^ sender,
          System::EventArgs ^ e)
       {
          // Add event handler code here.
       }
    ```

3. <span data-ttu-id="d4c9f-109">Добавьте код в обработчик событий в зависимости от приложения.</span><span class="sxs-lookup"><span data-stu-id="d4c9f-109">Add code to the event handler as appropriate to your application.</span></span>

4. <span data-ttu-id="d4c9f-110">Определите форму или элемент управления, для которого необходимо создать обработчик событий.</span><span class="sxs-lookup"><span data-stu-id="d4c9f-110">Determine which form or control you want to create an event handler for.</span></span>

5. <span data-ttu-id="d4c9f-111">В методе внутри класса формы добавьте код, в соответствии с которым обработчик событий будет обрабатывать событие.</span><span class="sxs-lookup"><span data-stu-id="d4c9f-111">In a method within your form's class, add code that specifies the event handler to handle the event.</span></span> <span data-ttu-id="d4c9f-112">Например, следующий код указывает обработчик событий `button1_Click` обрабатывающий событие <xref:System.Windows.Forms.Control.Click> элемента управления <xref:System.Windows.Forms.Button>:</span><span class="sxs-lookup"><span data-stu-id="d4c9f-112">For example, the following code specifies the event handler `button1_Click` handles the <xref:System.Windows.Forms.Control.Click> event of a <xref:System.Windows.Forms.Button> control:</span></span>

    ```vb
    AddHandler Button1.Click, AddressOf Button1_Click
    ```

    ```csharp
    button1.Click += new EventHandler(button1_Click);
    ```

    ```cpp
    button1->Click += gcnew System::EventHandler(this, &Form1::button1_Click);
    ```

     <span data-ttu-id="d4c9f-113">Метод <xref:System.ComponentModel.EventHandlerList.AddHandler%2A>, показанный в приведенном выше коде Visual Basic, устанавливает обработчик событий щелчка для кнопки.</span><span class="sxs-lookup"><span data-stu-id="d4c9f-113">The <xref:System.ComponentModel.EventHandlerList.AddHandler%2A> method demonstrated in the Visual Basic code above establishes a click event handler for the button.</span></span>

## <a name="see-also"></a><span data-ttu-id="d4c9f-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="d4c9f-114">See also</span></span>

- [<span data-ttu-id="d4c9f-115">Создание обработчиков событий в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d4c9f-115">Creating Event Handlers in Windows Forms</span></span>](creating-event-handlers-in-windows-forms.md)
- [<span data-ttu-id="d4c9f-116">Общие сведения об обработчиках событий</span><span class="sxs-lookup"><span data-stu-id="d4c9f-116">Event Handlers Overview</span></span>](event-handlers-overview-windows-forms.md)
- [<span data-ttu-id="d4c9f-117">Устранение неполадок, связанных с унаследованными обработчиками событий, в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d4c9f-117">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>](../../visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)
