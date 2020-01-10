---
title: Имена сборок и библиотек DLL
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- names [.NET Framework], DLLs
- names [.NET Framework], assemblies
- assemblies [.NET Framework], names
- DLLs, names
ms.assetid: e800b610-31b4-4949-9c14-cb60e9f254be
ms.openlocfilehash: eebccba0b923b04333f289a85330d190c31013ab
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709261"
---
# <a name="names-of-assemblies-and-dlls"></a>Имена сборок и библиотек DLL
Сборка — это единица развертывания и идентификации для программ управляемого кода. Хотя сборки могут охватывать один или несколько файлов, обычно сборка сопоставляет один к одному с библиотекой DLL. Поэтому в этом разделе описываются только соглашения об именовании библиотек DLL, которые затем можно сопоставить с соглашениями об именовании сборок.  
  
 **✓ DO** выбирать имена DLL-библиотек, указывающие на больших объемов функциональные возможности, например System.Data сборки.  
  
 Имена сборок и библиотек DLL не должны соответствовать именам пространств имен, но при именовании сборок разумно следовать имени пространства имен. Хорошим правилом Thumb является имя библиотеки DLL на основе общего префикса пространств имен, содержащихся в сборке. Например, сборка с двумя пространствами имен, `MyCompany.MyTechnology.FirstFeature` и `MyCompany.MyTechnology.SecondFeature`, может быть вызвана `MyCompany.MyTechnology.dll`.  
  
 **✓ CONSIDER** об именовании библиотек DLL по следующему шаблону:  
  
 `<Company>.<Component>.dll`  
  
 где `<Component>` содержит одно или несколько предложений, разделенных точкой. Например:  
  
 `Litware.Controls.dll`.  
  
 *Части © 2005, 2009 Корпорация Майкрософт. Все права защищены.*  
  
 *Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*  
  
## <a name="see-also"></a>См. также:

- [Рекомендации по проектированию на основе Framework](../../../docs/standard/design-guidelines/index.md)
- [Правила именования](../../../docs/standard/design-guidelines/naming-guidelines.md)
