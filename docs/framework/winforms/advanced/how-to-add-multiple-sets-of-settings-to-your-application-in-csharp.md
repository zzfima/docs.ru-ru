---
title: Как Добавление нескольких наборов параметров в приложение на C#
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], multiple sets
- application settings [Windows Forms], C#
ms.assetid: 45007ac6-cf07-4be7-bc38-3f0ef962faf9
ms.openlocfilehash: c6842d11c04e905d42734af939f2c3f0cfeacd47
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040130"
---
# <a name="how-to-add-multiple-sets-of-settings-to-your-application-in-c"></a><span data-ttu-id="e933d-102">Как Добавление нескольких наборов параметров в приложение на языке C\#</span><span class="sxs-lookup"><span data-stu-id="e933d-102">How To: Add Multiple Sets of Settings To Your Application in C\#</span></span>

<span data-ttu-id="e933d-103">В некоторых случаях может потребоваться несколько наборов параметров в приложении.</span><span class="sxs-lookup"><span data-stu-id="e933d-103">In some cases, you might want to have multiple sets of settings in an application.</span></span> <span data-ttu-id="e933d-104">Например, при разработке приложения, в котором определенная группа параметров будет часто изменяться, может быть разумно разделить их на один файл, чтобы файл можно было заменить оптовой, при этом другие параметры не затрагиваются.</span><span class="sxs-lookup"><span data-stu-id="e933d-104">For example, if you are developing an application where a particular group of settings is expected to change frequently, it might be wise to separate them all into a single file so that the file can be replaced wholesale, leaving other settings unaffected.</span></span> <span data-ttu-id="e933d-105">Visual Studio позволяет добавлять в проект несколько наборов параметров.</span><span class="sxs-lookup"><span data-stu-id="e933d-105">Visual Studio allows you to add multiple sets of settings to your project.</span></span> <span data-ttu-id="e933d-106">Доступ к дополнительным наборам параметров можно получить `Properties.Settings` через объект.</span><span class="sxs-lookup"><span data-stu-id="e933d-106">Additional sets of settings can be accessed via the `Properties.Settings` object.</span></span>

## <a name="add-an-additional-set-of-settings"></a><span data-ttu-id="e933d-107">Добавление дополнительного набора параметров</span><span class="sxs-lookup"><span data-stu-id="e933d-107">Add an Additional Set of Settings</span></span>

1. <span data-ttu-id="e933d-108">В Visual Studio в меню **проект** выберите команду **Добавить новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="e933d-108">In Visual Studio, from the **Project** menu, choose **Add New Item**.</span></span>

   <span data-ttu-id="e933d-109">Откроется диалоговое окно **Добавление нового элемента**.</span><span class="sxs-lookup"><span data-stu-id="e933d-109">The **Add New Item** dialog box opens.</span></span>

2. <span data-ttu-id="e933d-110">В диалоговом окне **Добавление нового элемента** выберите **файл параметров**, введите имя файла и нажмите кнопку **добавить** , чтобы добавить новый файл параметров в решение.</span><span class="sxs-lookup"><span data-stu-id="e933d-110">In the **Add New Item** dialog box, select **Settings File**, enter a name for the file, and click **Add** to add a new settings file to your solution.</span></span>

3. <span data-ttu-id="e933d-111">В **Обозреватель решений**перетащите новый файл параметров в папку **свойства** .</span><span class="sxs-lookup"><span data-stu-id="e933d-111">In **Solution Explorer**, drag the new Settings file into the **Properties** folder.</span></span> <span data-ttu-id="e933d-112">Это позволит сделать новые параметры доступными в коде.</span><span class="sxs-lookup"><span data-stu-id="e933d-112">This allows your new settings to be available in code.</span></span>

4. <span data-ttu-id="e933d-113">Добавьте и используйте параметры в этом файле так же, как и любые другие файлы параметров.</span><span class="sxs-lookup"><span data-stu-id="e933d-113">Add and use settings in this file as you would any other settings file.</span></span> <span data-ttu-id="e933d-114">Доступ к этой группе параметров можно получить с `Properties.Settings` помощью объекта.</span><span class="sxs-lookup"><span data-stu-id="e933d-114">You can access this group of settings via the `Properties.Settings` object.</span></span>

## <a name="see-also"></a><span data-ttu-id="e933d-115">См. также</span><span class="sxs-lookup"><span data-stu-id="e933d-115">See also</span></span>

- [<span data-ttu-id="e933d-116">Использование параметров приложения и параметров пользователя</span><span class="sxs-lookup"><span data-stu-id="e933d-116">Using Application Settings and User Settings</span></span>](using-application-settings-and-user-settings.md)
- [<span data-ttu-id="e933d-117">Общие сведения о параметрах приложений</span><span class="sxs-lookup"><span data-stu-id="e933d-117">Application Settings Overview</span></span>](application-settings-overview.md)
