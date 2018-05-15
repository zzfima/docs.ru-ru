---
title: '&#39;&lt;Имя интерфейса&gt;.&lt; имя пользователя&gt; &#39; уже реализован базовым классом &#39; &lt;имя_базового_класса&gt;&#39;. Повторная реализация &lt;тип&gt; предполагается, что'
ms.date: 07/20/2015
f1_keywords:
- vbc42015
- bc42015
helpviewer_keywords:
- BC42015
ms.assetid: 658c070a-113e-4bd8-b294-12c243191160
ms.openlocfilehash: 9054c293ede9db4637f23579407f2f76db29f2ba
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="39ltinterfacenamegtltmembernamegt39-is-already-implemented-by-the-base-class-39ltbaseclassnamegt39-re-implementation-of-lttypegt-assumed"></a><span data-ttu-id="16be6-103">&#39;&lt;Имя интерфейса&gt;.&lt; имя пользователя&gt; &#39; уже реализован базовым классом &#39; &lt;имя_базового_класса&gt;&#39;.</span><span class="sxs-lookup"><span data-stu-id="16be6-103">&#39;&lt;interfacename&gt;.&lt;membername&gt;&#39; is already implemented by the base class &#39;&lt;baseclassname&gt;&#39;.</span></span> <span data-ttu-id="16be6-104">Повторная реализация &lt;тип&gt; предполагается, что</span><span class="sxs-lookup"><span data-stu-id="16be6-104">Re-implementation of &lt;type&gt; assumed</span></span>
<span data-ttu-id="16be6-105">Свойство, процедура или событие в производном классе использует `Implements` предложение указания элемента интерфейса, который уже реализован в базовом классе.</span><span class="sxs-lookup"><span data-stu-id="16be6-105">A property, procedure, or event in a derived class uses an `Implements` clause specifying an interface member that is already implemented in the base class.</span></span>  
  
 <span data-ttu-id="16be6-106">Производный класс может повторно реализовать элемент интерфейса, который реализован его базовым классом.</span><span class="sxs-lookup"><span data-stu-id="16be6-106">A derived class can reimplement an interface member that is implemented by its base class.</span></span> <span data-ttu-id="16be6-107">Это не та же переопределяющая реализация базового класса.</span><span class="sxs-lookup"><span data-stu-id="16be6-107">This is not the same as overriding the base class implementation.</span></span> <span data-ttu-id="16be6-108">Дополнительные сведения см. в разделе [реализует](../../../visual-basic/language-reference/statements/implements-clause.md).</span><span class="sxs-lookup"><span data-stu-id="16be6-108">For more information, see [Implements](../../../visual-basic/language-reference/statements/implements-clause.md).</span></span>  
  
 <span data-ttu-id="16be6-109">По умолчанию данное сообщение является предупреждением.</span><span class="sxs-lookup"><span data-stu-id="16be6-109">By default, this message is a warning.</span></span> <span data-ttu-id="16be6-110">Сведения о сокрытии предупреждений или обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="16be6-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="16be6-111">**Идентификатор ошибки:** BC42015</span><span class="sxs-lookup"><span data-stu-id="16be6-111">**Error ID:** BC42015</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="16be6-112">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="16be6-112">To correct this error</span></span>  
  
-   <span data-ttu-id="16be6-113">Если вы собираетесь реализовать элемент интерфейса, вам не нужно предпринимать никаких действий.</span><span class="sxs-lookup"><span data-stu-id="16be6-113">If you intend to reimplement the interface member, you do not need to take any action.</span></span> <span data-ttu-id="16be6-114">Код в производном классе получает доступ к повторно реализованному элементу, если вы используете `MyBase` ключевое слово для доступа к реализации базового класса.</span><span class="sxs-lookup"><span data-stu-id="16be6-114">Code in your derived class accesses the reimplemented member unless you use the `MyBase` keyword to access the base class implementation.</span></span>  
  
-   <span data-ttu-id="16be6-115">Если вы не собираетесь реализовать элемент интерфейса, удалите предложение `Implements` из свойства, процедуры или объявления события.</span><span class="sxs-lookup"><span data-stu-id="16be6-115">If you do not intend to reimplement the interface member, remove the `Implements` clause from the property, procedure, or event declaration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16be6-116">См. также</span><span class="sxs-lookup"><span data-stu-id="16be6-116">See Also</span></span>  
 [<span data-ttu-id="16be6-117">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="16be6-117">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
