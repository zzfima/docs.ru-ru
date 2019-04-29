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
author: KrzysztofCwalina
ms.openlocfilehash: 7d940f10799df2efc6c6d031781e1ef7cf777dd6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61937401"
---
# <a name="protected-members"></a><span data-ttu-id="492dd-102">Защищенные члены</span><span class="sxs-lookup"><span data-stu-id="492dd-102">Protected Members</span></span>
<span data-ttu-id="492dd-103">Защищенные члены сами по себе не предоставляют все расширения, но они могут сделать расширяемости через подклассы более мощные.</span><span class="sxs-lookup"><span data-stu-id="492dd-103">Protected members by themselves do not provide any extensibility, but they can make extensibility through subclassing more powerful.</span></span> <span data-ttu-id="492dd-104">Они могут использоваться для предоставления Дополнительные параметры настройки без усложнять основной открытый интерфейс.</span><span class="sxs-lookup"><span data-stu-id="492dd-104">They can be used to expose advanced customization options without unnecessarily complicating the main public interface.</span></span>  
  
 <span data-ttu-id="492dd-105">Конструкторы Framework нужно очень осторожно защищенные члены, поскольку имя «защищен» можно предоставить ложное чувство защищенности.</span><span class="sxs-lookup"><span data-stu-id="492dd-105">Framework designers need to be careful with protected members because the name "protected" can give a false sense of security.</span></span> <span data-ttu-id="492dd-106">Любой пользователь может подкласс Незапечатанный класс и доступ к защищенным членам, и поэтому те же защитных приемы программирования, используемый для открытых членов применяются к защищенным членам.</span><span class="sxs-lookup"><span data-stu-id="492dd-106">Anyone is able to subclass an unsealed class and access protected members, and so all the same defensive coding practices used for public members apply to protected members.</span></span>  
  
 <span data-ttu-id="492dd-107">**✓ CONSIDER** с помощью защищенные члены для расширенной настройки.</span><span class="sxs-lookup"><span data-stu-id="492dd-107">**✓ CONSIDER** using protected members for advanced customization.</span></span>  
  
 <span data-ttu-id="492dd-108">**✓ DO** обрабатывать защищенные члены незапечатанных классов как открытые с целью анализа безопасности, документацию и совместимости.</span><span class="sxs-lookup"><span data-stu-id="492dd-108">**✓ DO** treat protected members in unsealed classes as public for the purpose of security, documentation, and compatibility analysis.</span></span>  
  
 <span data-ttu-id="492dd-109">Любой пользователь может наследовать от класса и доступа к защищенным членам.</span><span class="sxs-lookup"><span data-stu-id="492dd-109">Anyone can inherit from a class and access the protected members.</span></span>  
  
 <span data-ttu-id="492dd-110">*Фрагменты: © Корпорация Майкрософт (Microsoft Corporation), 2005, 2009. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="492dd-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="492dd-111">*Перепечатано разрешением Пирсона для образовательных учреждений, Inc. из [рекомендации по разработке Framework: Условные обозначения, стили и шаблоны для библиотеки .NET для повторного использования, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Кшиштов Квалина и Брэд Абрамс, опубликованных 22 октября 2008 г., издательство Addison-Wesley Professional как части цикла разработки Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="492dd-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="492dd-112">См. также</span><span class="sxs-lookup"><span data-stu-id="492dd-112">See also</span></span>

- [<span data-ttu-id="492dd-113">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="492dd-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="492dd-114">Разработка с обеспечением расширяемости</span><span class="sxs-lookup"><span data-stu-id="492dd-114">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
