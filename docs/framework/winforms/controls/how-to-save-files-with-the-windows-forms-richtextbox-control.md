---
title: Практическое руководство. Сохранение файлов с помощью элемента управления RichTextBox в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- saving files
- RTF files [Windows Forms], saving in RichTextBox control
- examples [Windows Forms], text boxes
- saving files [Windows Forms], RichTextBox control
- files [Windows Forms], saving with RichTextBox control
- RichTextBox control [Windows Forms], saving files
- .rtf files [Windows Forms], saving in RichTextBox control
- text files [Windows Forms], saving from RichTextBox control
ms.assetid: 4a58ec19-84d1-4383-9110-298c06adcfca
ms.openlocfilehash: c50b2f3309c1f811b29e824327a709e2cc4bd791
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33536199"
---
# <a name="how-to-save-files-with-the-windows-forms-richtextbox-control"></a><span data-ttu-id="a6d82-102">Практическое руководство. Сохранение файлов с помощью элемента управления RichTextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a6d82-102">How to: Save Files with the Windows Forms RichTextBox Control</span></span>
<span data-ttu-id="a6d82-103">Windows Forms <xref:System.Windows.Forms.RichTextBox> управления может записывать информацию, он отображается в одном из следующих форматов:</span><span class="sxs-lookup"><span data-stu-id="a6d82-103">The Windows Forms <xref:System.Windows.Forms.RichTextBox> control can write the information it displays in one of several formats:</span></span>  
  
-   <span data-ttu-id="a6d82-104">Обычный текст</span><span class="sxs-lookup"><span data-stu-id="a6d82-104">Plain text</span></span>  
  
-   <span data-ttu-id="a6d82-105">Текст в Юникоде</span><span class="sxs-lookup"><span data-stu-id="a6d82-105">Unicode plain text</span></span>  
  
-   <span data-ttu-id="a6d82-106">Текст в формате (RTF)</span><span class="sxs-lookup"><span data-stu-id="a6d82-106">Rich-Text Format (RTF)</span></span>  
  
-   <span data-ttu-id="a6d82-107">Формат RTF с пропусками OLE-объекты</span><span class="sxs-lookup"><span data-stu-id="a6d82-107">RTF with spaces in place of OLE objects</span></span>  
  
-   <span data-ttu-id="a6d82-108">Обычный текст с текстовым представлением объектов OLE</span><span class="sxs-lookup"><span data-stu-id="a6d82-108">Plain text with a textual representation of OLE objects</span></span>  
  
 <span data-ttu-id="a6d82-109">Чтобы сохранить файл, вызовите <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="a6d82-109">To save a file, call the <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> method.</span></span> <span data-ttu-id="a6d82-110">Можно также использовать **SaveFile** метод для сохранения данных в поток.</span><span class="sxs-lookup"><span data-stu-id="a6d82-110">You can also use the **SaveFile** method to save data to a stream.</span></span> <span data-ttu-id="a6d82-111">Дополнительные сведения см. в разделе <xref:System.Windows.Forms.RichTextBox.SaveFile%28System.IO.Stream%2CSystem.Windows.Forms.RichTextBoxStreamType%29>.</span><span class="sxs-lookup"><span data-stu-id="a6d82-111">For more information, see <xref:System.Windows.Forms.RichTextBox.SaveFile%28System.IO.Stream%2CSystem.Windows.Forms.RichTextBoxStreamType%29>.</span></span>  
  
### <a name="to-save-the-contents-of-the-control-to-a-file"></a><span data-ttu-id="a6d82-112">Чтобы сохранить содержимое элемента управления в файл</span><span class="sxs-lookup"><span data-stu-id="a6d82-112">To save the contents of the control to a file</span></span>  
  
1.  <span data-ttu-id="a6d82-113">Определите путь к файлу для сохранения.</span><span class="sxs-lookup"><span data-stu-id="a6d82-113">Determine the path of the file to be saved.</span></span>  
  
     <span data-ttu-id="a6d82-114">Чтобы сделать это в реальном приложении, обычно используется <xref:System.Windows.Forms.SaveFileDialog> компонента.</span><span class="sxs-lookup"><span data-stu-id="a6d82-114">To do this in a real-world application, you would typically use the <xref:System.Windows.Forms.SaveFileDialog> component.</span></span> <span data-ttu-id="a6d82-115">Общие сведения см. в разделе [Общие сведения о компоненте SaveFileDialog](../../../../docs/framework/winforms/controls/savefiledialog-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="a6d82-115">For an overview, see [SaveFileDialog Component Overview](../../../../docs/framework/winforms/controls/savefiledialog-component-overview-windows-forms.md).</span></span>  
  
2.  <span data-ttu-id="a6d82-116">Вызовите <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> метод <xref:System.Windows.Forms.RichTextBox> управления, указав имя файла для сохранения и, при необходимости, тип файла.</span><span class="sxs-lookup"><span data-stu-id="a6d82-116">Call the <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> method of the <xref:System.Windows.Forms.RichTextBox> control, specifying the file to save and optionally a file type.</span></span> <span data-ttu-id="a6d82-117">Если вызвать метод с именем файла только аргументом, файл будет сохранен как RTF.</span><span class="sxs-lookup"><span data-stu-id="a6d82-117">If you call the method with a file name as its only argument, the file will be saved as RTF.</span></span> <span data-ttu-id="a6d82-118">Чтобы указать другой тип файла, вызовите метод со значением перечисления <xref:System.Windows.Forms.RichTextBoxStreamType> в качестве второго аргумента.</span><span class="sxs-lookup"><span data-stu-id="a6d82-118">To specify another file type, call the method with a value of the <xref:System.Windows.Forms.RichTextBoxStreamType> enumeration as its second argument.</span></span>  
  
     <span data-ttu-id="a6d82-119">В приведенном ниже примере путь задан при размещении RTF-файл является **Мои документы** папки.</span><span class="sxs-lookup"><span data-stu-id="a6d82-119">In the example below, the path set for the location of the rich-text file is the **My Documents** folder.</span></span> <span data-ttu-id="a6d82-120">Это расположение используется, так как предполагается, что большинство компьютеров под управлением операционной системы Windows будет содержать эта папка.</span><span class="sxs-lookup"><span data-stu-id="a6d82-120">This location is used because you can assume that most computers running the Windows operating system will include this folder.</span></span> <span data-ttu-id="a6d82-121">Эта папка также позволяет уровень доступа к системе минимальной безопасно запустить приложение.</span><span class="sxs-lookup"><span data-stu-id="a6d82-121">Choosing this location also allows users with minimal system access levels to safely run the application.</span></span> <span data-ttu-id="a6d82-122">В приведенном ниже примере предполагается наличие формы с <xref:System.Windows.Forms.RichTextBox> управления уже добавлен.</span><span class="sxs-lookup"><span data-stu-id="a6d82-122">The example below assumes a form with a <xref:System.Windows.Forms.RichTextBox> control already added.</span></span>  
  
    ```vb  
    Public Sub SaveFile()  
       ' You should replace the bold file name in the   
       ' sample below with a file name of your own choosing.  
       RichTextBox1.SaveFile(System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\Testdoc.rtf", _  
          RichTextBoxStreamType.RichNoOleObjs)  
    End Sub  
    ```  
  
    ```csharp  
    public void SaveFile()  
    {  
       // You should replace the bold file name in the   
       // sample below with a file name of your own choosing.  
       // Note the escape character used (@) when specifying the path.  
       richTextBox1.SaveFile(System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.Personal)  
       + @"\Testdoc.rtf",  
          RichTextBoxStreamType.RichNoOleObjs);  
    }  
    ```  
  
    ```cpp  
    public:  
       void SaveFile()  
       {  
          // You should replace the bold file name in the   
          // sample below with a file name of your own choosing.  
          richTextBox1->SaveFile(String::Concat  
             (System::Environment::GetFolderPath  
             (System::Environment::SpecialFolder::Personal),  
             "\\Testdoc.rtf"), RichTextBoxStreamType::RichNoOleObjs);  
       }  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="a6d82-123">В этом примере создается файл (если файл отсутствует).</span><span class="sxs-lookup"><span data-stu-id="a6d82-123">This example creates a new file, if the file does not already exist.</span></span> <span data-ttu-id="a6d82-124">Если приложению требуется создать файл, что ему необходимо иметь доступ к папке.</span><span class="sxs-lookup"><span data-stu-id="a6d82-124">If an application needs to create a file, that application needs Create access for the folder.</span></span> <span data-ttu-id="a6d82-125">Для задания разрешений используются списки управления доступом.</span><span class="sxs-lookup"><span data-stu-id="a6d82-125">Permissions are set using access control lists.</span></span> <span data-ttu-id="a6d82-126">Если файл уже существует, приложению требуется только доступ на запись, меньшими привилегиями.</span><span class="sxs-lookup"><span data-stu-id="a6d82-126">If the file already exists, the application needs only Write access, a lesser privilege.</span></span> <span data-ttu-id="a6d82-127">Если это возможно, безопаснее создать файл во время развертывания и только предоставляет доступ на чтение в одном файле, а не создавать доступа для папки.</span><span class="sxs-lookup"><span data-stu-id="a6d82-127">Where possible, it is more secure to create the file during deployment, and only grant Read access to a single file, rather than Create access for a folder.</span></span> <span data-ttu-id="a6d82-128">По тем же соображениям рекомендуется записывать данные в пользовательские папки, а не в коревую папку или папку Program Files.</span><span class="sxs-lookup"><span data-stu-id="a6d82-128">Also, it is more secure to write data to user folders than to the root folder or the Program Files folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6d82-129">См. также</span><span class="sxs-lookup"><span data-stu-id="a6d82-129">See Also</span></span>  
 <xref:System.Windows.Forms.RichTextBox.SaveFile%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.RichTextBox>  
 [<span data-ttu-id="a6d82-130">Элемент управления RichTextBox</span><span class="sxs-lookup"><span data-stu-id="a6d82-130">RichTextBox Control</span></span>](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)  
 [<span data-ttu-id="a6d82-131">Элементы управления для использования в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a6d82-131">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
