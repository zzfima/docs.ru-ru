---
title: "&quot;&lt;interfacename&gt;.&lt; имя пользователя&gt;«уже реализован базовым классом»&lt;baseclassname&gt;&quot;. Повторная реализация &lt;тип&gt; предполагается, что | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc42015
- bc42015
dev_langs:
- VB
helpviewer_keywords:
- BC42015
ms.assetid: 658c070a-113e-4bd8-b294-12c243191160
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: d792485f13e2b675858d82aa7219670a17fd974e
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="39ltinterfacenamegtltmembernamegt39-is-already-implemented-by-the-base-class-39ltbaseclassnamegt39-re-implementation-of-lttypegt-assumed"></a><span data-ttu-id="8f396-103">"&lt;interfacename&gt;.&lt; имя пользователя&gt;«уже реализован базовым классом»&lt;baseclassname&gt;".</span><span class="sxs-lookup"><span data-stu-id="8f396-103">&#39;&lt;interfacename&gt;.&lt;membername&gt;&#39; is already implemented by the base class &#39;&lt;baseclassname&gt;&#39;.</span></span> <span data-ttu-id="8f396-104">Повторная реализация &lt;тип&gt; предполагается, что</span><span class="sxs-lookup"><span data-stu-id="8f396-104">Re-implementation of &lt;type&gt; assumed</span></span>
<span data-ttu-id="8f396-105">Свойство, процедура или событие в производном классе использует `Implements` предложение указания элемента интерфейса, который уже реализован в базовом классе.</span><span class="sxs-lookup"><span data-stu-id="8f396-105">A property, procedure, or event in a derived class uses an `Implements` clause specifying an interface member that is already implemented in the base class.</span></span>  
  
 <span data-ttu-id="8f396-106">Производный класс может повторно реализовать элемент интерфейса, который реализован его базовым классом.</span><span class="sxs-lookup"><span data-stu-id="8f396-106">A derived class can reimplement an interface member that is implemented by its base class.</span></span> <span data-ttu-id="8f396-107">Это не та же переопределяющая реализация базового класса.</span><span class="sxs-lookup"><span data-stu-id="8f396-107">This is not the same as overriding the base class implementation.</span></span> <span data-ttu-id="8f396-108">Дополнительные сведения см. в разделе [реализует](../../../visual-basic/language-reference/statements/implements-clause.md).</span><span class="sxs-lookup"><span data-stu-id="8f396-108">For more information, see [Implements](../../../visual-basic/language-reference/statements/implements-clause.md).</span></span>  
  
 <span data-ttu-id="8f396-109">По умолчанию данное сообщение является предупреждением.</span><span class="sxs-lookup"><span data-stu-id="8f396-109">By default, this message is a warning.</span></span> <span data-ttu-id="8f396-110">Сведения о сокрытии предупреждений или обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="8f396-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="8f396-111">**Идентификатор ошибки:** BC42015</span><span class="sxs-lookup"><span data-stu-id="8f396-111">**Error ID:** BC42015</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="8f396-112">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="8f396-112">To correct this error</span></span>  
  
-   <span data-ttu-id="8f396-113">Если вы собираетесь реализовать элемент интерфейса, вам не нужно предпринимать никаких действий.</span><span class="sxs-lookup"><span data-stu-id="8f396-113">If you intend to reimplement the interface member, you do not need to take any action.</span></span> <span data-ttu-id="8f396-114">Код в производном классе получает повторно реализованный элемент, без использования `MyBase` ключевое слово для доступа к реализации базового класса.</span><span class="sxs-lookup"><span data-stu-id="8f396-114">Code in your derived class accesses the reimplemented member unless you use the `MyBase` keyword to access the base class implementation.</span></span>  
  
-   <span data-ttu-id="8f396-115">Если вы не собираетесь реализовать элемент интерфейса, удалите предложение `Implements` из свойства, процедуры или объявления события.</span><span class="sxs-lookup"><span data-stu-id="8f396-115">If you do not intend to reimplement the interface member, remove the `Implements` clause from the property, procedure, or event declaration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f396-116">См. также</span><span class="sxs-lookup"><span data-stu-id="8f396-116">See Also</span></span>  
 [<span data-ttu-id="8f396-117">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="8f396-117">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
