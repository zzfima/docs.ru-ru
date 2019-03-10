---
title: Практическое руководство. Создание обработчиков событий во время выполнения для форм Windows Forms
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
ms.openlocfilehash: 7ebafd745290a40fa6f4f83910fb32d67cdcff75
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57705272"
---
# <a name="how-to-create-event-handlers-at-run-time-for-windows-forms"></a><span data-ttu-id="1061c-102">Практическое руководство. Создание обработчиков событий во время выполнения для форм Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1061c-102">How to: Create Event Handlers at Run Time for Windows Forms</span></span>
<span data-ttu-id="1061c-103">Помимо создания событий с помощью конструктора Windows Forms можно также создать обработчик событий во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="1061c-103">In addition to creating events using the Windows Forms Designer, you can also create an event handler at run time.</span></span> <span data-ttu-id="1061c-104">Это позволит подключать обработчики событий в зависимости от условий в коде во время выполнения, а не при начальном запуске программы.</span><span class="sxs-lookup"><span data-stu-id="1061c-104">This action allows you to connect event handlers based on conditions in code at run time as opposed to having them connected when the program initially starts.</span></span>  
  
### <a name="to-create-an-event-handler-at-run-time"></a><span data-ttu-id="1061c-105">Создание обработчика событий во время выполнения</span><span class="sxs-lookup"><span data-stu-id="1061c-105">To create an event handler at run time</span></span>  
  
1.  <span data-ttu-id="1061c-106">Откройте форму в редакторе кода, в которую необходимо добавить обработчик событий.</span><span class="sxs-lookup"><span data-stu-id="1061c-106">Open the form in the Code Editor that you want to add an event handler to.</span></span>  
  
2.  <span data-ttu-id="1061c-107">Добавьте метод в форму с сигнатурой метода для события, которое будет необходимо обрабатывать.</span><span class="sxs-lookup"><span data-stu-id="1061c-107">Add a method to your form with the method signature for the event that you want to handle.</span></span>  
  
     <span data-ttu-id="1061c-108">Например, для обработки <xref:System.Windows.Forms.Control.Click> событие <xref:System.Windows.Forms.Button> элемента управления, необходимо создать метод, подобный следующему:</span><span class="sxs-lookup"><span data-stu-id="1061c-108">For example, if you were handling the <xref:System.Windows.Forms.Control.Click> event of a <xref:System.Windows.Forms.Button> control, you would create a method such as the following:</span></span>  
  
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
  
3.  <span data-ttu-id="1061c-109">Добавьте код в обработчик событий в зависимости от приложения.</span><span class="sxs-lookup"><span data-stu-id="1061c-109">Add code to the event handler as appropriate to your application.</span></span>  
  
4.  <span data-ttu-id="1061c-110">Определите форму или элемент управления, для которого необходимо создать обработчик событий.</span><span class="sxs-lookup"><span data-stu-id="1061c-110">Determine which form or control you want to create an event handler for.</span></span>  
  
5.  <span data-ttu-id="1061c-111">В методе внутри класса формы добавьте код, в соответствии с которым обработчик событий будет обрабатывать событие.</span><span class="sxs-lookup"><span data-stu-id="1061c-111">In a method within your form's class, add code that specifies the event handler to handle the event.</span></span> <span data-ttu-id="1061c-112">Например, следующий код задает обработчик событий `button1_Click` дескрипторы <xref:System.Windows.Forms.Control.Click> событие <xref:System.Windows.Forms.Button> управления:</span><span class="sxs-lookup"><span data-stu-id="1061c-112">For example, the following code specifies the event handler `button1_Click` handles the <xref:System.Windows.Forms.Control.Click> event of a <xref:System.Windows.Forms.Button> control:</span></span>  
  
    ```vb  
    AddHandler Button1.Click, AddressOf Button1_Click  
    ```  
  
    ```csharp  
    button1.Click += new EventHandler(button1_Click);  
    ```  
  
    ```cpp  
    button1->Click += gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
     <span data-ttu-id="1061c-113"><xref:System.ComponentModel.EventHandlerList.AddHandler%2A> Метод демонстрируется в приведенном выше коде Visual Basic, устанавливает обработчик событий щелчка для кнопки.</span><span class="sxs-lookup"><span data-stu-id="1061c-113">The <xref:System.ComponentModel.EventHandlerList.AddHandler%2A> method demonstrated in the Visual Basic code above establishes a click event handler for the button.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1061c-114">См. также</span><span class="sxs-lookup"><span data-stu-id="1061c-114">See also</span></span>
- [<span data-ttu-id="1061c-115">Создание обработчиков событий в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1061c-115">Creating Event Handlers in Windows Forms</span></span>](creating-event-handlers-in-windows-forms.md)
- [<span data-ttu-id="1061c-116">Общие сведения об обработчиках событий</span><span class="sxs-lookup"><span data-stu-id="1061c-116">Event Handlers Overview</span></span>](event-handlers-overview-windows-forms.md)
- [<span data-ttu-id="1061c-117">Устранение неполадок, связанных с унаследованными обработчиками событий, в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1061c-117">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)
