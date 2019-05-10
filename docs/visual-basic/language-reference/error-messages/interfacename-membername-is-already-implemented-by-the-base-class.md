---
title: "'<interfacename>. <membername>«уже реализован базовым классом»<baseclassname>\". Повторная реализация <type> предполагается, что"
ms.date: 07/20/2015
f1_keywords:
- vbc42015
- bc42015
helpviewer_keywords:
- BC42015
ms.assetid: 658c070a-113e-4bd8-b294-12c243191160
ms.openlocfilehash: 5943eff5fa7e68da9905e3e589eea264c06943c1
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64593321"
---
# <a name="interfacenamemembername-is-already-implemented-by-the-base-class-baseclassname-re-implementation-of-type-assumed"></a><span data-ttu-id="dd478-103">"\<имя_интерфейса >. \<имя_члена > "уже реализован базовым классом\<имя_базового_класса >".</span><span class="sxs-lookup"><span data-stu-id="dd478-103">'\<interfacename>.\<membername>' is already implemented by the base class '\<baseclassname>'.</span></span> <span data-ttu-id="dd478-104">Повторная реализация \<тип > предполагается, что</span><span class="sxs-lookup"><span data-stu-id="dd478-104">Re-implementation of \<type> assumed</span></span>
<span data-ttu-id="dd478-105">Свойство, процедура или событие в производном классе использует `Implements` предложение, задающее элемент интерфейса, который уже реализован в базовом классе.</span><span class="sxs-lookup"><span data-stu-id="dd478-105">A property, procedure, or event in a derived class uses an `Implements` clause specifying an interface member that is already implemented in the base class.</span></span>  
  
 <span data-ttu-id="dd478-106">Производный класс может повторно реализовать элемент интерфейса, который реализован его базовым классом.</span><span class="sxs-lookup"><span data-stu-id="dd478-106">A derived class can reimplement an interface member that is implemented by its base class.</span></span> <span data-ttu-id="dd478-107">Это не та же переопределяющая реализация базового класса.</span><span class="sxs-lookup"><span data-stu-id="dd478-107">This is not the same as overriding the base class implementation.</span></span> <span data-ttu-id="dd478-108">Для получения дополнительной информации см. [Implements](../../../visual-basic/language-reference/statements/implements-clause.md).</span><span class="sxs-lookup"><span data-stu-id="dd478-108">For more information, see [Implements](../../../visual-basic/language-reference/statements/implements-clause.md).</span></span>  
  
 <span data-ttu-id="dd478-109">По умолчанию данное сообщение является предупреждением.</span><span class="sxs-lookup"><span data-stu-id="dd478-109">By default, this message is a warning.</span></span> <span data-ttu-id="dd478-110">Сведения о сокрытии предупреждений или обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="dd478-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="dd478-111">**Идентификатор ошибки:** BC42015</span><span class="sxs-lookup"><span data-stu-id="dd478-111">**Error ID:** BC42015</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="dd478-112">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="dd478-112">To correct this error</span></span>  
  
- <span data-ttu-id="dd478-113">Если вы собираетесь реализовать элемент интерфейса, вам не нужно предпринимать никаких действий.</span><span class="sxs-lookup"><span data-stu-id="dd478-113">If you intend to reimplement the interface member, you do not need to take any action.</span></span> <span data-ttu-id="dd478-114">Код в производном классе получает доступ к повторно реализованному элементу только при использовании `MyBase` ключевое слово для доступа к реализации базового класса.</span><span class="sxs-lookup"><span data-stu-id="dd478-114">Code in your derived class accesses the reimplemented member unless you use the `MyBase` keyword to access the base class implementation.</span></span>  
  
- <span data-ttu-id="dd478-115">Если вы не собираетесь реализовать элемент интерфейса, удалите предложение `Implements` из свойства, процедуры или объявления события.</span><span class="sxs-lookup"><span data-stu-id="dd478-115">If you do not intend to reimplement the interface member, remove the `Implements` clause from the property, procedure, or event declaration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd478-116">См. также</span><span class="sxs-lookup"><span data-stu-id="dd478-116">See also</span></span>

- [<span data-ttu-id="dd478-117">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="dd478-117">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
