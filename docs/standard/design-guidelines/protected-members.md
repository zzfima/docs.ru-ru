---
title: Защищенные члены
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- members [.NET Framework], protected
- protected members
- classes [.NET Framework], unsealed
- classes [.NET Framework], protected members
- unsealed classes
- customizing class behavior
ms.assetid: aa0b58ee-3956-494d-ab48-471ae5db8740
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4574dffc3f9dd1b60d655bfde33a4ddc1a81d350
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44140948"
---
# <a name="protected-members"></a><span data-ttu-id="2ee79-102">Защищенные члены</span><span class="sxs-lookup"><span data-stu-id="2ee79-102">Protected Members</span></span>
<span data-ttu-id="2ee79-103">Защищенные члены сами по себе не предоставляют все расширения, но они могут сделать расширяемости через подклассы более мощные.</span><span class="sxs-lookup"><span data-stu-id="2ee79-103">Protected members by themselves do not provide any extensibility, but they can make extensibility through subclassing more powerful.</span></span> <span data-ttu-id="2ee79-104">Они могут использоваться для предоставления Дополнительные параметры настройки без усложнять основной открытый интерфейс.</span><span class="sxs-lookup"><span data-stu-id="2ee79-104">They can be used to expose advanced customization options without unnecessarily complicating the main public interface.</span></span>  
  
 <span data-ttu-id="2ee79-105">Конструкторы Framework нужно очень осторожно защищенные члены, поскольку имя «защищен» можно предоставить ложное чувство защищенности.</span><span class="sxs-lookup"><span data-stu-id="2ee79-105">Framework designers need to be careful with protected members because the name "protected" can give a false sense of security.</span></span> <span data-ttu-id="2ee79-106">Любой пользователь может подкласс Незапечатанный класс и доступ к защищенным членам, и поэтому те же защитных приемы программирования, используемый для открытых членов применяются к защищенным членам.</span><span class="sxs-lookup"><span data-stu-id="2ee79-106">Anyone is able to subclass an unsealed class and access protected members, and so all the same defensive coding practices used for public members apply to protected members.</span></span>  
  
 <span data-ttu-id="2ee79-107">**✓ CONSIDER** с помощью защищенные члены для расширенной настройки.</span><span class="sxs-lookup"><span data-stu-id="2ee79-107">**✓ CONSIDER** using protected members for advanced customization.</span></span>  
  
 <span data-ttu-id="2ee79-108">**✓ DO** обрабатывать защищенные члены незапечатанных классов как открытые с целью анализа безопасности, документацию и совместимости.</span><span class="sxs-lookup"><span data-stu-id="2ee79-108">**✓ DO** treat protected members in unsealed classes as public for the purpose of security, documentation, and compatibility analysis.</span></span>  
  
 <span data-ttu-id="2ee79-109">Любой пользователь может наследовать от класса и доступа к защищенным членам.</span><span class="sxs-lookup"><span data-stu-id="2ee79-109">Anyone can inherit from a class and access the protected members.</span></span>  
  
 <span data-ttu-id="2ee79-110">*Фрагменты: © Корпорация Майкрософт (Microsoft Corporation), 2005, 2009. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="2ee79-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="2ee79-111">*Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="2ee79-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ee79-112">См. также</span><span class="sxs-lookup"><span data-stu-id="2ee79-112">See also</span></span>

- [<span data-ttu-id="2ee79-113">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="2ee79-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
- [<span data-ttu-id="2ee79-114">Разработка с обеспечением расширяемости</span><span class="sxs-lookup"><span data-stu-id="2ee79-114">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
