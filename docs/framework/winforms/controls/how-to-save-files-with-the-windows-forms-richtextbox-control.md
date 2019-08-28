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
ms.openlocfilehash: c5d88e4942d96ee12e8b9f40156090c874386668
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046263"
---
# <a name="how-to-save-files-with-the-windows-forms-richtextbox-control"></a><span data-ttu-id="987da-102">Практическое руководство. Сохранение файлов с помощью элемента управления RichTextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="987da-102">How to: Save Files with the Windows Forms RichTextBox Control</span></span>

<span data-ttu-id="987da-103">Элемент управления <xref:System.Windows.Forms.RichTextBox> Windows Forms может записывать отображаемые сведения в одном из следующих форматов:</span><span class="sxs-lookup"><span data-stu-id="987da-103">The Windows Forms <xref:System.Windows.Forms.RichTextBox> control can write the information it displays in one of several formats:</span></span>

- <span data-ttu-id="987da-104">Обычный текст</span><span class="sxs-lookup"><span data-stu-id="987da-104">Plain text</span></span>

- <span data-ttu-id="987da-105">Обычный текст в Юникоде</span><span class="sxs-lookup"><span data-stu-id="987da-105">Unicode plain text</span></span>

- <span data-ttu-id="987da-106">Формат RTF</span><span class="sxs-lookup"><span data-stu-id="987da-106">Rich-Text Format (RTF)</span></span>

- <span data-ttu-id="987da-107">RTF с пробелами вместо объектов OLE</span><span class="sxs-lookup"><span data-stu-id="987da-107">RTF with spaces in place of OLE objects</span></span>

- <span data-ttu-id="987da-108">Обычный текст с текстовым представлением объектов OLE</span><span class="sxs-lookup"><span data-stu-id="987da-108">Plain text with a textual representation of OLE objects</span></span>

<span data-ttu-id="987da-109">Чтобы сохранить файл, вызовите <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="987da-109">To save a file, call the <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> method.</span></span> <span data-ttu-id="987da-110">Можно также использовать метод **SaveFile** для сохранения данных в поток.</span><span class="sxs-lookup"><span data-stu-id="987da-110">You can also use the **SaveFile** method to save data to a stream.</span></span> <span data-ttu-id="987da-111">Дополнительные сведения см. в разделе <xref:System.Windows.Forms.RichTextBox.SaveFile%28System.IO.Stream%2CSystem.Windows.Forms.RichTextBoxStreamType%29>.</span><span class="sxs-lookup"><span data-stu-id="987da-111">For more information, see <xref:System.Windows.Forms.RichTextBox.SaveFile%28System.IO.Stream%2CSystem.Windows.Forms.RichTextBoxStreamType%29>.</span></span>

### <a name="to-save-the-contents-of-the-control-to-a-file"></a><span data-ttu-id="987da-112">Сохранение содержимого элемента управления в файле</span><span class="sxs-lookup"><span data-stu-id="987da-112">To save the contents of the control to a file</span></span>

1. <span data-ttu-id="987da-113">Определите путь к файлу, который необходимо сохранить.</span><span class="sxs-lookup"><span data-stu-id="987da-113">Determine the path of the file to be saved.</span></span>

    <span data-ttu-id="987da-114">Для этого в реальном приложении обычно используется <xref:System.Windows.Forms.SaveFileDialog> компонент.</span><span class="sxs-lookup"><span data-stu-id="987da-114">To do this in a real-world application, you would typically use the <xref:System.Windows.Forms.SaveFileDialog> component.</span></span> <span data-ttu-id="987da-115">Общие сведения см. в разделе [Общие сведения о компоненте SaveFileDialog](savefiledialog-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="987da-115">For an overview, see [SaveFileDialog Component Overview](savefiledialog-component-overview-windows-forms.md).</span></span>

2. <span data-ttu-id="987da-116">Вызовите <xref:System.Windows.Forms.RichTextBox> метод элемента управления, указав файл для сохранения и, при необходимости, тип файла. <xref:System.Windows.Forms.RichTextBox.SaveFile%2A></span><span class="sxs-lookup"><span data-stu-id="987da-116">Call the <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> method of the <xref:System.Windows.Forms.RichTextBox> control, specifying the file to save and optionally a file type.</span></span> <span data-ttu-id="987da-117">При вызове метода с именем файла в качестве единственного аргумента файл будет сохранен как RTF.</span><span class="sxs-lookup"><span data-stu-id="987da-117">If you call the method with a file name as its only argument, the file will be saved as RTF.</span></span> <span data-ttu-id="987da-118">Чтобы указать другой тип файла, вызовите метод со значением перечисления <xref:System.Windows.Forms.RichTextBoxStreamType> в качестве второго аргумента.</span><span class="sxs-lookup"><span data-stu-id="987da-118">To specify another file type, call the method with a value of the <xref:System.Windows.Forms.RichTextBoxStreamType> enumeration as its second argument.</span></span>

    <span data-ttu-id="987da-119">В приведенном ниже примере путь, заданный для расположения RTF-файла, является папкой " **Мои документы** ".</span><span class="sxs-lookup"><span data-stu-id="987da-119">In the example below, the path set for the location of the rich-text file is the **My Documents** folder.</span></span> <span data-ttu-id="987da-120">Это расположение используется, поскольку можно предположить, что большинство компьютеров, работающих под управлением операционной системы Windows, будут содержать эту папку.</span><span class="sxs-lookup"><span data-stu-id="987da-120">This location is used because you can assume that most computers running the Windows operating system will include this folder.</span></span> <span data-ttu-id="987da-121">Выбор этого расположения также позволяет пользователям с минимальными уровнями доступа к системе безопасно запускать приложение.</span><span class="sxs-lookup"><span data-stu-id="987da-121">Choosing this location also allows users with minimal system access levels to safely run the application.</span></span> <span data-ttu-id="987da-122">В приведенном ниже примере предполагается, <xref:System.Windows.Forms.RichTextBox> что форма с уже добавленным элементом управления.</span><span class="sxs-lookup"><span data-stu-id="987da-122">The example below assumes a form with a <xref:System.Windows.Forms.RichTextBox> control already added.</span></span>

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
    > <span data-ttu-id="987da-123">В этом примере создается файл (если файл отсутствует).</span><span class="sxs-lookup"><span data-stu-id="987da-123">This example creates a new file, if the file does not already exist.</span></span> <span data-ttu-id="987da-124">Если приложению требуется создать файл, этому приложению требуется доступ для создания папки.</span><span class="sxs-lookup"><span data-stu-id="987da-124">If an application needs to create a file, that application needs Create access for the folder.</span></span> <span data-ttu-id="987da-125">Для задания разрешений используются списки управления доступом.</span><span class="sxs-lookup"><span data-stu-id="987da-125">Permissions are set using access control lists.</span></span> <span data-ttu-id="987da-126">Если файл уже существует, приложению требуется только доступ на запись, чем меньше привилегия.</span><span class="sxs-lookup"><span data-stu-id="987da-126">If the file already exists, the application needs only Write access, a lesser privilege.</span></span> <span data-ttu-id="987da-127">Там, где это возможно, более безопасно создавать файл во время развертывания и предоставлять доступ только для чтения к одному файлу, а не к папке.</span><span class="sxs-lookup"><span data-stu-id="987da-127">Where possible, it is more secure to create the file during deployment, and only grant Read access to a single file, rather than Create access for a folder.</span></span> <span data-ttu-id="987da-128">По тем же соображениям рекомендуется записывать данные в пользовательские папки, а не в коревую папку или папку Program Files.</span><span class="sxs-lookup"><span data-stu-id="987da-128">Also, it is more secure to write data to user folders than to the root folder or the Program Files folder.</span></span>

## <a name="see-also"></a><span data-ttu-id="987da-129">См. также</span><span class="sxs-lookup"><span data-stu-id="987da-129">See also</span></span>

- <xref:System.Windows.Forms.RichTextBox.SaveFile%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.RichTextBox>
- [<span data-ttu-id="987da-130">Элемент управления RichTextBox</span><span class="sxs-lookup"><span data-stu-id="987da-130">RichTextBox Control</span></span>](richtextbox-control-windows-forms.md)
- [<span data-ttu-id="987da-131">Элементы управления для использования в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="987da-131">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
