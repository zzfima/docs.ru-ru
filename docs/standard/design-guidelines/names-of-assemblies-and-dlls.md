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
ms.openlocfilehash: f3c5997f777c937e9726b271afa0ae6d7a19b37d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744170"
---
# <a name="names-of-assemblies-and-dlls"></a>Имена сборок и библиотек DLL
Сборка — это единица развертывания и идентификации для программ управляемого кода. Хотя сборки могут охватывать один или несколько файлов, обычно сборка сопоставляет один к одному с библиотекой DLL. Поэтому в этом разделе описываются только соглашения об именовании библиотек DLL, которые затем можно сопоставить с соглашениями об именовании сборок.

 ✔️ выбрать имена для библиотек DLL сборки, которые предлагают большие фрагменты функциональности, такие как System. Data.

 Имена сборок и библиотек DLL не должны соответствовать именам пространств имен, но при именовании сборок разумно следовать имени пространства имен. Хорошим правилом Thumb является имя библиотеки DLL на основе общего префикса пространств имен, содержащихся в сборке. Например, сборка с двумя пространствами имен, `MyCompany.MyTechnology.FirstFeature` и `MyCompany.MyTechnology.SecondFeature`, может быть вызвана `MyCompany.MyTechnology.dll`.

 ✔️ Рассмотрите возможность именования библиотек DLL в соответствии со следующим шаблоном:

 `<Company>.<Component>.dll`

 где `<Component>` содержит одно или несколько предложений, разделенных точкой. Пример:

 `Litware.Controls.dll`.

 *Части © 2005, 2009 Корпорация Майкрософт. Все права защищены.*

 *Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*

## <a name="see-also"></a>См. также раздел

- [Рекомендации по проектированию на основе Framework](../../../docs/standard/design-guidelines/index.md)
- [Правила именования](../../../docs/standard/design-guidelines/naming-guidelines.md)
