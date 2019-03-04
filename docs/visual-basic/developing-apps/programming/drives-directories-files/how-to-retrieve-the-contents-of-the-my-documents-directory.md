---
title: Как выполнить Извлечение содержимого каталога "Мои документы" в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- My Documents directory
ms.assetid: 26560d01-7dda-4457-8e95-21db23d71aea
ms.openlocfilehash: 6d4e0bc7d300b2553d5286600cc65b7c494359b9
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56964189"
---
# <a name="how-to-retrieve-the-contents-of-the-my-documents-directory-in-visual-basic"></a><span data-ttu-id="2c1de-102">Как выполнить Извлечение содержимого каталога "Мои документы" в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2c1de-102">How to: Retrieve the Contents of the My Documents Directory in Visual Basic</span></span>
<span data-ttu-id="2c1de-103">Объект <xref:Microsoft.VisualBasic.FileIO.SpecialDirectories> можно использовать для чтения из различных каталогов **Все пользователи**, таких как **Мои документы** или **Рабочий стол**.</span><span class="sxs-lookup"><span data-stu-id="2c1de-103">The <xref:Microsoft.VisualBasic.FileIO.SpecialDirectories> object can be used to read from many of the **All Users** directories, such as **My Documents** or **Desktop**.</span></span>  
  
### <a name="to-read-from-the-my-documents-folder"></a><span data-ttu-id="2c1de-104">Чтение из папки "Мои документы"</span><span class="sxs-lookup"><span data-stu-id="2c1de-104">To read from the My Documents folder</span></span>  
  
-   <span data-ttu-id="2c1de-105">Для чтения текста из каждого файла в определенном каталоге используйте метод `ReadAllText`.</span><span class="sxs-lookup"><span data-stu-id="2c1de-105">Use the `ReadAllText` method to read the text from each file in a specific directory.</span></span> <span data-ttu-id="2c1de-106">В следующем коде определяется каталог и файл, а затем применяется метод `ReadAllText`, который считывает данные в строку с именем `patients`.</span><span class="sxs-lookup"><span data-stu-id="2c1de-106">The following code specifies a directory and file and then uses `ReadAllText` to read them into the string named `patients`.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#15)]  
  
## <a name="see-also"></a><span data-ttu-id="2c1de-107">См. также</span><span class="sxs-lookup"><span data-stu-id="2c1de-107">See also</span></span>
- <xref:Microsoft.VisualBasic.FileIO.SpecialDirectories>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllText%2A>
