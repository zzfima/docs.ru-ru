---
title: Практическое руководство. Доступ к членам объекта (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- members [Visual Basic], accessing
- object variables [Visual Basic], accessing members
ms.assetid: a0072514-6a79-4dd6-8d03-ca8c13e61ddc
ms.openlocfilehash: de00e428cc3d9d7a5688e853b0ff4295fec5b3e9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62052135"
---
# <a name="how-to-access-members-of-an-object-visual-basic"></a><span data-ttu-id="146fc-102">Практическое руководство. Доступ к членам объекта (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="146fc-102">How to: Access Members of an Object (Visual Basic)</span></span>
<span data-ttu-id="146fc-103">При наличии объектную переменную, которая ссылается на объект, часто требуется для работы с членами этого объекта, например методы, свойства, поля и события.</span><span class="sxs-lookup"><span data-stu-id="146fc-103">When you have an object variable that refers to an object, you often want to work with the members of that object, such as its methods, properties, fields, and events.</span></span> <span data-ttu-id="146fc-104">Например, когда вы создадите новый <xref:System.Windows.Forms.Form> объекта, может потребоваться задать его <xref:System.Windows.Forms.Control.Text%2A> свойства или вызов его <xref:System.Windows.Forms.Control.Focus%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="146fc-104">For example, once you have created a new <xref:System.Windows.Forms.Form> object, you might want to set its <xref:System.Windows.Forms.Control.Text%2A> property or call its <xref:System.Windows.Forms.Control.Focus%2A> method.</span></span>  
  
## <a name="accessing-members"></a><span data-ttu-id="146fc-105">Доступ к членам</span><span class="sxs-lookup"><span data-stu-id="146fc-105">Accessing Members</span></span>  
 <span data-ttu-id="146fc-106">Доступ к членам объекта осуществляется через переменную, которая ссылается на него.</span><span class="sxs-lookup"><span data-stu-id="146fc-106">You access an object's members through the variable that refers to it.</span></span>  
  
#### <a name="to-access-members-of-an-object"></a><span data-ttu-id="146fc-107">Для доступа к членам объекта</span><span class="sxs-lookup"><span data-stu-id="146fc-107">To access members of an object</span></span>  
  
- <span data-ttu-id="146fc-108">Оператор доступа к членам (`.`) между именем переменной объекта и имя члена.</span><span class="sxs-lookup"><span data-stu-id="146fc-108">Use the member-access operator (`.`) between the object variable name and the member name.</span></span>  
  
    ```  
    currentText = newForm.Text  
    ```  
  
     <span data-ttu-id="146fc-109">Если член является [Shared](../../../../visual-basic/language-reference/modifiers/shared.md), нет необходимости переменной для доступа к нему.</span><span class="sxs-lookup"><span data-stu-id="146fc-109">If the member is [Shared](../../../../visual-basic/language-reference/modifiers/shared.md), you do not need a variable to access it.</span></span>  
  
## <a name="accessing-members-of-an-object-of-known-type"></a><span data-ttu-id="146fc-110">Доступ к членам объекта известного типа</span><span class="sxs-lookup"><span data-stu-id="146fc-110">Accessing Members of an Object of Known Type</span></span>  
 <span data-ttu-id="146fc-111">Если вы знаете тип объекта во время компиляции, можно использовать *раннее связывание* переменной, которая ссылается на него.</span><span class="sxs-lookup"><span data-stu-id="146fc-111">If you know the type of an object at compile time, you can use *early binding* for a variable that refers to it.</span></span>  
  
#### <a name="to-access-members-of-an-object-for-which-you-know-the-type-at-compile-time"></a><span data-ttu-id="146fc-112">Для доступа к членам объекта, для которого вы знаете тип во время компиляции</span><span class="sxs-lookup"><span data-stu-id="146fc-112">To access members of an object for which you know the type at compile time</span></span>  
  
1. <span data-ttu-id="146fc-113">Объявите переменную объекта типа объекта, который требуется присвоить переменной.</span><span class="sxs-lookup"><span data-stu-id="146fc-113">Declare the object variable to be of the type of the object you intend to assign to the variable.</span></span>  
  
    ```  
    Dim extraForm As System.Windows.Forms.Form  
    ```  
  
     <span data-ttu-id="146fc-114">С помощью `Option Strict On`, можно назначить только <xref:System.Windows.Forms.Form> объектов (или объекты типа, производного от <xref:System.Windows.Forms.Form>) для `extraForm`.</span><span class="sxs-lookup"><span data-stu-id="146fc-114">With `Option Strict On`, you can assign only <xref:System.Windows.Forms.Form> objects (or objects of a type derived from <xref:System.Windows.Forms.Form>) to `extraForm`.</span></span> <span data-ttu-id="146fc-115">Если вы определили класса или структуры с помощью расширяющего `CType` преобразование в <xref:System.Windows.Forms.Form>, можно также назначить класс или структуру `extraForm`.</span><span class="sxs-lookup"><span data-stu-id="146fc-115">If you have defined a class or structure with a widening `CType` conversion to <xref:System.Windows.Forms.Form>, you can also assign that class or structure to `extraForm`.</span></span>  
  
2. <span data-ttu-id="146fc-116">Оператор доступа к членам (`.`) между именем переменной объекта и имя члена.</span><span class="sxs-lookup"><span data-stu-id="146fc-116">Use the member-access operator (`.`) between the object variable name and the member name.</span></span>  
  
    ```  
    extraForm.Show()  
    ```  
  
     <span data-ttu-id="146fc-117">Вам доступны все методы и свойства, относящиеся к <xref:System.Windows.Forms.Form> класса, независимо от того, что `Option Strict` параметр.</span><span class="sxs-lookup"><span data-stu-id="146fc-117">You can access all of the methods and properties specific to the <xref:System.Windows.Forms.Form> class, no matter what the `Option Strict` setting is.</span></span>  
  
## <a name="accessing-members-of-an-object-of-unknown-type"></a><span data-ttu-id="146fc-118">Доступ к членам объекта неизвестного типа</span><span class="sxs-lookup"><span data-stu-id="146fc-118">Accessing Members of an Object of Unknown Type</span></span>  
 <span data-ttu-id="146fc-119">Если вы не знаете тип объекта во время компиляции, необходимо использовать *позднее связывание* для любой переменной, которая ссылается на него.</span><span class="sxs-lookup"><span data-stu-id="146fc-119">If you do not know the type of an object at compile time, you must use *late binding* for any variable that refers to it.</span></span>  
  
#### <a name="to-access-members-of-an-object-for-which-you-do-not-know-the-type-at-compile-time"></a><span data-ttu-id="146fc-120">Для доступа к членам объекта, для которого вы не знаете тип во время компиляции</span><span class="sxs-lookup"><span data-stu-id="146fc-120">To access members of an object for which you do not know the type at compile time</span></span>  
  
1. <span data-ttu-id="146fc-121">Объявите переменную объекта с [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="146fc-121">Declare the object variable to be of the [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md).</span></span> <span data-ttu-id="146fc-122">(Объявление переменной как `Object` совпадает со значением его объявление как <xref:System.Object?displayProperty=nameWithType>.)</span><span class="sxs-lookup"><span data-stu-id="146fc-122">(Declaring a variable as `Object` is the same as declaring it as <xref:System.Object?displayProperty=nameWithType>.)</span></span>  
  
    ```  
    Dim someControl As Object  
    ```  
  
     <span data-ttu-id="146fc-123">С помощью `Option Strict On`, доступны только члены, определенные для <xref:System.Object> класса.</span><span class="sxs-lookup"><span data-stu-id="146fc-123">With `Option Strict On`, you can access only the members that are defined on the <xref:System.Object> class.</span></span>  
  
2. <span data-ttu-id="146fc-124">Оператор доступа к членам (`.`) между именем переменной объекта и имя члена.</span><span class="sxs-lookup"><span data-stu-id="146fc-124">Use the member-access operator (`.`) between the object variable name and the member name.</span></span>  
  
    ```  
    someControl.GetType()  
    ```  
  
     <span data-ttu-id="146fc-125">Чтобы иметь возможность доступа к членам любого объекта, можно присвоить переменной объекта, необходимо задать `Option Strict Off`.</span><span class="sxs-lookup"><span data-stu-id="146fc-125">To be able to access the members of any object you assign to the object variable, you must set `Option Strict Off`.</span></span> <span data-ttu-id="146fc-126">При этом компилятор не может гарантировать, что данный элемент предоставляется с помощью объекта, можно присвоить переменной.</span><span class="sxs-lookup"><span data-stu-id="146fc-126">When you do this, the compiler cannot guarantee that a given member is exposed by the object you assign to the variable.</span></span> <span data-ttu-id="146fc-127">Если объект не предоставляет членом попытки обращения к, <xref:System.MemberAccessException> возникает исключение.</span><span class="sxs-lookup"><span data-stu-id="146fc-127">If the object does not expose a member you attempt to access, a <xref:System.MemberAccessException> exception occurs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="146fc-128">См. также</span><span class="sxs-lookup"><span data-stu-id="146fc-128">See also</span></span>

- <xref:System.Object>
- <xref:System.Windows.Forms.Form>
- <xref:System.MemberAccessException>
- [<span data-ttu-id="146fc-129">Объектные переменные</span><span class="sxs-lookup"><span data-stu-id="146fc-129">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="146fc-130">Объявление объектной переменной</span><span class="sxs-lookup"><span data-stu-id="146fc-130">Object Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [<span data-ttu-id="146fc-131">Тип данных Object</span><span class="sxs-lookup"><span data-stu-id="146fc-131">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="146fc-132">Оператор Option Strict</span><span class="sxs-lookup"><span data-stu-id="146fc-132">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
