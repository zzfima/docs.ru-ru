---
title: Практическое руководство. Выгрузка файла
ms.date: 07/20/2015
helpviewer_keywords:
- networks, uploading files
- files [Visual Basic], uploading
- uploading files [Visual Basic]
- UploadFile method [Visual Basic]
- My.Computer.Network.UploadFile method
ms.assetid: a8b37924-c523-4fd3-b5ca-cb0074df29cd
ms.openlocfilehash: 52b731606c74ab7ff06a42dfdbe078616ba33d88
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "74345559"
---
# <a name="how-to-upload-a-file-in-visual-basic"></a><span data-ttu-id="79870-102">Практическое руководство. Передача файла в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="79870-102">How to: Upload a File in Visual Basic</span></span>

<span data-ttu-id="79870-103">Метод <xref:Microsoft.VisualBasic.Devices.Network.UploadFile%2A> можно использовать для отправки файла и сохранения его в удаленном расположении.</span><span class="sxs-lookup"><span data-stu-id="79870-103">The <xref:Microsoft.VisualBasic.Devices.Network.UploadFile%2A> method can be used to upload a file and store it to a remote location.</span></span> <span data-ttu-id="79870-104">Если для параметра `ShowUI` установлено значение `True`, отображается диалоговое окно, показывающее ход загрузки и позволяющее пользователю отменить операцию.</span><span class="sxs-lookup"><span data-stu-id="79870-104">If the `ShowUI` parameter is set to `True`, a dialog box is displayed that shows the progress of the upload and allows users to cancel the operation.</span></span>  
  
### <a name="to-upload-a-file"></a><span data-ttu-id="79870-105">Передача файла</span><span class="sxs-lookup"><span data-stu-id="79870-105">To upload a file</span></span>  
  
- <span data-ttu-id="79870-106">Для передачи файла используйте метод `UploadFile`, указав расположение исходного файла и каталога назначения в виде строки или URI. В этом примере файл `Order.txt` передается на веб-узел `http://www.cohowinery.com/uploads.aspx`.</span><span class="sxs-lookup"><span data-stu-id="79870-106">Use the `UploadFile` method to upload a file, specifying the source file's location and the target directory location as a string or URI (Uniform Resource Identifier).This example uploads the file `Order.txt` to `http://www.cohowinery.com/uploads.aspx`.</span></span>  
  
     [!code-vb[VbResourceTasks#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#6)]  
  
### <a name="to-upload-a-file-and-show-the-progress-of-the-operation"></a><span data-ttu-id="79870-107">Передача файла с отображением хода выполнения операции</span><span class="sxs-lookup"><span data-stu-id="79870-107">To upload a file and show the progress of the operation</span></span>  
  
- <span data-ttu-id="79870-108">Для передачи файла используйте метод `UploadFile`, указав расположение исходного файла и каталога назначения в виде строки или URI.</span><span class="sxs-lookup"><span data-stu-id="79870-108">Use the `UploadFile` method to upload a file, specifying the source file's location and the target directory location as a string or URI.</span></span> <span data-ttu-id="79870-109">В этом примере файл `Order.txt` передается на веб-узел `http://www.cohowinery.com/uploads.aspx` без указания имени пользователя или пароля, при этом отображается ход передачи. Время ожидания равно 500 миллисекундам.</span><span class="sxs-lookup"><span data-stu-id="79870-109">This example uploads the file `Order.txt` to `http://www.cohowinery.com/uploads.aspx` without supplying a user name or password, shows the progress of the upload, and has a time-out interval of 500 milliseconds.</span></span>  
  
     [!code-vb[VbResourceTasks#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#7)]  
  
### <a name="to-upload-a-file-supplying-a-user-name-and-password"></a><span data-ttu-id="79870-110">Передача файла с указанием имени пользователя и пароля</span><span class="sxs-lookup"><span data-stu-id="79870-110">To upload a file, supplying a user name and password</span></span>  
  
- <span data-ttu-id="79870-111">Для передачи файла используйте метод `UploadFile`, указав расположение исходного файла и каталога назначения в виде строки или URI, а также имя пользователя и пароль.</span><span class="sxs-lookup"><span data-stu-id="79870-111">Use the `UploadFile` method to upload a file, specifying the source file's location and the target directory location as a string or URI, and specifying the user name and the password.</span></span> <span data-ttu-id="79870-112">В этом примере файл `Order.txt` передается на веб-узел `http://www.cohowinery.com/uploads.aspx` с указанием имени пользователя `anonymous` и пустого пароля.</span><span class="sxs-lookup"><span data-stu-id="79870-112">This example uploads the file `Order.txt` to `http://www.cohowinery.com/uploads.aspx`, supplying the user name `anonymous` and a blank password.</span></span>  
  
     [!code-vb[VbResourceTasks#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#8)]  
  
## <a name="robust-programming"></a><span data-ttu-id="79870-113">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="79870-113">Robust Programming</span></span>  

 <span data-ttu-id="79870-114">Исключение может возникнуть при следующих условиях:</span><span class="sxs-lookup"><span data-stu-id="79870-114">The following conditions may throw an exception:</span></span>  
  
- <span data-ttu-id="79870-115">Недопустимый путь к локальному файлу (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="79870-115">The local file path is not valid (<xref:System.ArgumentException>).</span></span>  
  
- <span data-ttu-id="79870-116">Сбой проверки подлинности (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="79870-116">Authentication failed (<xref:System.Security.SecurityException>).</span></span>  
  
- <span data-ttu-id="79870-117">Время ожидания соединения истекло (<xref:System.TimeoutException>).</span><span class="sxs-lookup"><span data-stu-id="79870-117">The connection timed out (<xref:System.TimeoutException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79870-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="79870-118">See also</span></span>

- <xref:Microsoft.VisualBasic.Devices.Network?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Devices.Network.UploadFile%2A>
- [<span data-ttu-id="79870-119">Практическое руководство. Скачивание файла</span><span class="sxs-lookup"><span data-stu-id="79870-119">How to: Download a File</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-download-a-file.md)
- [<span data-ttu-id="79870-120">Практическое руководство. Анализ путей к файлам</span><span class="sxs-lookup"><span data-stu-id="79870-120">How to: Parse File Paths</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)
