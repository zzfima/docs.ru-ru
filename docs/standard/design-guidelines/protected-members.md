---
title: Защищенные члены
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- members [.NET Framework], protected
- protected members
- classes [.NET Framework], unsealed
- classes [.NET Framework], protected members
- unsealed classes
- customizing class behavior
ms.assetid: aa0b58ee-3956-494d-ab48-471ae5db8740
ms.openlocfilehash: 14ef02a760c9d4b77fe058334baffd63fcf29cfd
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709105"
---
# <a name="protected-members"></a><span data-ttu-id="d1d40-102">Защищенные члены</span><span class="sxs-lookup"><span data-stu-id="d1d40-102">Protected Members</span></span>
<span data-ttu-id="d1d40-103">Защищенные члены сами по себе не предоставляют расширяемости, но они могут обеспечивать расширяемость с помощью подкласса.</span><span class="sxs-lookup"><span data-stu-id="d1d40-103">Protected members by themselves do not provide any extensibility, but they can make extensibility through subclassing more powerful.</span></span> <span data-ttu-id="d1d40-104">Они могут использоваться для предоставления расширенных возможностей настройки без необходимости усложнения основного общедоступного интерфейса.</span><span class="sxs-lookup"><span data-stu-id="d1d40-104">They can be used to expose advanced customization options without unnecessarily complicating the main public interface.</span></span>  
  
 <span data-ttu-id="d1d40-105">Разработчикам платформ необходимо соблюдать осторожность при использовании защищенных членов, поскольку имя "Protected" может дать ложный смысл безопасности.</span><span class="sxs-lookup"><span data-stu-id="d1d40-105">Framework designers need to be careful with protected members because the name "protected" can give a false sense of security.</span></span> <span data-ttu-id="d1d40-106">Любой пользователь может создать подкласс для незапечатанного класса и доступа к защищенным членам, поэтому все те же методы кодирования, используемые для открытых членов, применяются к защищенным членам.</span><span class="sxs-lookup"><span data-stu-id="d1d40-106">Anyone is able to subclass an unsealed class and access protected members, and so all the same defensive coding practices used for public members apply to protected members.</span></span>  
  
 <span data-ttu-id="d1d40-107">**✓ CONSIDER** с помощью защищенные члены для расширенной настройки.</span><span class="sxs-lookup"><span data-stu-id="d1d40-107">**✓ CONSIDER** using protected members for advanced customization.</span></span>  
  
 <span data-ttu-id="d1d40-108">**✓ DO** обрабатывать защищенные члены незапечатанных классов как открытые с целью анализа безопасности, документацию и совместимости.</span><span class="sxs-lookup"><span data-stu-id="d1d40-108">**✓ DO** treat protected members in unsealed classes as public for the purpose of security, documentation, and compatibility analysis.</span></span>  
  
 <span data-ttu-id="d1d40-109">Любой пользователь может наследовать от класса и получить доступ к защищенным членам.</span><span class="sxs-lookup"><span data-stu-id="d1d40-109">Anyone can inherit from a class and access the protected members.</span></span>  
  
 <span data-ttu-id="d1d40-110">*Части © 2005, 2009 Корпорация Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="d1d40-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="d1d40-111">*Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="d1d40-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1d40-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="d1d40-112">See also</span></span>

- [<span data-ttu-id="d1d40-113">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="d1d40-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="d1d40-114">Разработка с обеспечением расширяемости</span><span class="sxs-lookup"><span data-stu-id="d1d40-114">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
