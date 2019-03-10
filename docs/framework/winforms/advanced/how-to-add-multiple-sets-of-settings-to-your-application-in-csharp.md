---
title: 'Как выполнить: Добавить несколько наборов параметров в приложениеC#'
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], multiple sets
- application settings [Windows Forms], C#
ms.assetid: 45007ac6-cf07-4be7-bc38-3f0ef962faf9
ms.openlocfilehash: 43402d8a1b0b1ca26e656be1424a5fa341ac4728
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57719654"
---
# <a name="how-to-add-multiple-sets-of-settings-to-your-application-in-c"></a><span data-ttu-id="c7981-102">Как выполнить: Добавление несколько наборов параметров в приложение на языке C\#</span><span class="sxs-lookup"><span data-stu-id="c7981-102">How To: Add Multiple Sets of Settings To Your Application in C\#</span></span>
<span data-ttu-id="c7981-103">В некоторых случаях вам может потребоваться несколько наборов параметров в приложении.</span><span class="sxs-lookup"><span data-stu-id="c7981-103">In some cases, you might want to have multiple sets of settings in an application.</span></span> <span data-ttu-id="c7981-104">К примеру Если вы разрабатываете приложения там, где ожидается определенная группа параметров изменяться чаще остальных, возможно, удобнее поместить их в один файл, чтобы его можно заменить, изменяя другие параметры.</span><span class="sxs-lookup"><span data-stu-id="c7981-104">For example, if you are developing an application where a particular group of settings is expected to change frequently, it might be wise to separate them all into a single file so that the file can be replaced wholesale, leaving other settings unaffected.</span></span> <span data-ttu-id="c7981-105">Visual Studio позволяет добавлять несколько наборов параметров в проект.</span><span class="sxs-lookup"><span data-stu-id="c7981-105">Visual Studio allows you to add multiple sets of settings to your project.</span></span> <span data-ttu-id="c7981-106">Дополнительные наборы параметров может осуществляться через объект Properties.Settings.</span><span class="sxs-lookup"><span data-stu-id="c7981-106">Additional sets of settings can be accessed via the Properties.Settings object.</span></span>  
  
### <a name="to-add-an-additional-set-of-setting-to-your-application"></a><span data-ttu-id="c7981-107">Чтобы добавить дополнительный набор параметров в приложение</span><span class="sxs-lookup"><span data-stu-id="c7981-107">To Add an Additional Set of Setting to your Application</span></span>  
  
1.  <span data-ttu-id="c7981-108">В меню **Проект** выберите команду **Добавить новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="c7981-108">From the **Project** menu, choose **Add New Item**.</span></span> <span data-ttu-id="c7981-109">Откроется диалоговое окно **Добавление нового элемента**.</span><span class="sxs-lookup"><span data-stu-id="c7981-109">The **Add New Item** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="c7981-110">В **Добавление нового элемента** выберите **файл параметров**, введите имя для файла и нажмите кнопку **добавить** для добавления в решение новый файл параметров.</span><span class="sxs-lookup"><span data-stu-id="c7981-110">In the **Add New Item** dialog box, select **Settings File**, type in a name for the file, and click **Add** to add a new settings file to your solution.</span></span>  
  
3.  <span data-ttu-id="c7981-111">В **обозревателе решений**, перетащите новый файл параметров в **свойства** папки.</span><span class="sxs-lookup"><span data-stu-id="c7981-111">In **Solution Explorer**, drag the new Settings file into the **Properties** folder.</span></span> <span data-ttu-id="c7981-112">Благодаря этому новые параметры будут доступны в коде.</span><span class="sxs-lookup"><span data-stu-id="c7981-112">This allows your new settings to be available in code.</span></span>  
  
4.  <span data-ttu-id="c7981-113">Добавить и использовать параметры в этом файле, как и любыми другими файлами параметров.</span><span class="sxs-lookup"><span data-stu-id="c7981-113">Add and use settings in this file as you would any other settings file.</span></span> <span data-ttu-id="c7981-114">Эта группа параметров с помощью объекта Properties.Settings доступны.</span><span class="sxs-lookup"><span data-stu-id="c7981-114">You can access this group of settings via the Properties.Settings object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7981-115">См. также</span><span class="sxs-lookup"><span data-stu-id="c7981-115">See also</span></span>
- [<span data-ttu-id="c7981-116">Использование параметров приложения и параметров пользователя</span><span class="sxs-lookup"><span data-stu-id="c7981-116">Using Application Settings and User Settings</span></span>](using-application-settings-and-user-settings.md)
- [<span data-ttu-id="c7981-117">Общие сведения о параметрах приложений</span><span class="sxs-lookup"><span data-stu-id="c7981-117">Application Settings Overview</span></span>](application-settings-overview.md)
