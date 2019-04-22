---
title: Как выполнить Чтение параметров приложения в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- reading application settings
- My.Settings object [Visual Basic], reading application settings
- application settings [Visual Basic], reading
ms.assetid: eb3428ef-115e-49a8-a878-e0613183fee0
ms.openlocfilehash: e7d909563ca7e991a51c2f921b5248aa587a83d7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58823588"
---
# <a name="how-to-read-application-settings-in-visual-basic"></a><span data-ttu-id="d4190-102">Как выполнить Чтение параметров приложения в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d4190-102">How to: Read Application Settings in Visual Basic</span></span>
<span data-ttu-id="d4190-103">Пользовательский параметр можно прочитать с помощью свойства объекта `My.Settings`.</span><span class="sxs-lookup"><span data-stu-id="d4190-103">You can read a user setting by accessing the setting's property on the `My.Settings` object.</span></span>  
  
 <span data-ttu-id="d4190-104">Объект `My.Settings` представляет каждый параметр в виде свойства.</span><span class="sxs-lookup"><span data-stu-id="d4190-104">The `My.Settings` object exposes each setting as a property.</span></span> <span data-ttu-id="d4190-105">Имя свойства совпадает с именем параметра, а тип свойства совпадает с типом параметра.</span><span class="sxs-lookup"><span data-stu-id="d4190-105">The property name is the same as the setting name, and the property type is the same as the setting type.</span></span> <span data-ttu-id="d4190-106">**Область** параметра определяет, доступно ли свойство только для чтения. Свойство для параметра с областью **Приложение** доступно только для чтения, а свойство для параметра с областью **Пользователь** доступно для чтения или записи.</span><span class="sxs-lookup"><span data-stu-id="d4190-106">The setting's **Scope** indicates if the property is read-only; the property for an **Application** scope setting is read-only, while the property for a **User** scope setting is read-write.</span></span> <span data-ttu-id="d4190-107">Дополнительные сведения см. в разделе [Объект My.Settings](../../../../visual-basic/language-reference/objects/my-settings-object.md).</span><span class="sxs-lookup"><span data-stu-id="d4190-107">For more information, see [My.Settings Object](../../../../visual-basic/language-reference/objects/my-settings-object.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d4190-108">Пример</span><span class="sxs-lookup"><span data-stu-id="d4190-108">Example</span></span>  
 <span data-ttu-id="d4190-109">В этом пример выводится значение параметра `Nickname`.</span><span class="sxs-lookup"><span data-stu-id="d4190-109">This example displays the value of the `Nickname` setting.</span></span>  
  
 [!code-vb[VbVbalrMyResources#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#14)]  
  
 <span data-ttu-id="d4190-110">Для надлежащего выполнения этого примера приложение должно иметь параметр `Nickname` типа `String`.</span><span class="sxs-lookup"><span data-stu-id="d4190-110">For this example to work, your application must have a `Nickname` setting, of type `String`.</span></span> <span data-ttu-id="d4190-111">Дополнительные сведения см. в разделе [Управление параметрами приложения (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span><span class="sxs-lookup"><span data-stu-id="d4190-111">For more information, see [Managing Application Settings (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4190-112">См. также</span><span class="sxs-lookup"><span data-stu-id="d4190-112">See also</span></span>

- [<span data-ttu-id="d4190-113">Объект My.Settings</span><span class="sxs-lookup"><span data-stu-id="d4190-113">My.Settings Object</span></span>](../../../../visual-basic/language-reference/objects/my-settings-object.md)
- [<span data-ttu-id="d4190-114">Практическое руководство. Изменение пользовательских параметров в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d4190-114">How to: Change User Settings in Visual Basic</span></span>](../../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)
- [<span data-ttu-id="d4190-115">Практическое руководство. Сохранение пользовательских параметров в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d4190-115">How to: Persist User Settings in Visual Basic</span></span>](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)
- [<span data-ttu-id="d4190-116">Практическое руководство. Создание таблицы свойств для пользовательских параметров в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d4190-116">How to: Create Property Grids for User Settings in Visual Basic</span></span>](../../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)
- [<span data-ttu-id="d4190-117">Управление параметрами приложения (.NET)</span><span class="sxs-lookup"><span data-stu-id="d4190-117">Managing Application Settings (.NET)</span></span>](/visualstudio/ide/managing-application-settings-dotnet)
