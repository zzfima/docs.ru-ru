---
title: Имена сборок и библиотек DLL
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- names [.NET Framework], DLLs
- names [.NET Framework], assemblies
- assemblies [.NET Framework], names
- DLLs, names
ms.assetid: e800b610-31b4-4949-9c14-cb60e9f254be
caps.latest.revision: 11
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: ff14d3d804329e591486a7eb2a2ee7ed430f622c
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2018
---
# <a name="names-of-assemblies-and-dlls"></a>Имена сборок и библиотек DLL
Сборка является единицей развертывания и удостоверение для управляемого кода программы. Несмотря на то, что сборки могут охватывать один или несколько файлов, обычно сборки однозначное сопоставление с библиотекой DLL. Таким образом в этом разделе описаны только DLL соглашения об именовании, которые затем можно сопоставить соглашения об именовании сборок.  
  
 **✓ СДЕЛАТЬ** выбирать имена DLL-библиотек, указывающие на больших объемов функциональные возможности, например System.Data сборки.  
  
 Имена сборки и библиотеки DLL не обязательно должны соответствовать именам пространств имен, но следует за именем пространства имен при именовании сборок. Хорошее проверенное правило является имя библиотеки DLL, в зависимости от общего префикса пространства имен, содержащиеся в сборке. Например, сборки с двумя пространствами имен `MyCompany.MyTechnology.FirstFeature` и `MyCompany.MyTechnology.SecondFeature`, можно вызвать `MyCompany.MyTechnology.dll`.  
  
 **✓ Попробуйте** об именовании библиотек DLL по следующему шаблону:  
  
 `<Company>.<Component>.dll`  
  
 где `<Component>` содержит одно или несколько предложений, разделенных точкой. Пример:  
  
 `Litware.Controls.dll`.  
  
 *Фрагменты © 2005, 2009 корпорации Майкрософт. Все права защищены.*  
  
 *Перепечатываются разрешении Пирсона для образовательных учреждений, Inc. из [Framework рекомендации по проектированию: условные обозначения, стили и шаблоны для библиотеки .NET для повторного использования, 2-е издание](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina и Брэд Абрамс, опубликованные 22 октября 2008 г., Addison-Wesley Professional в составе ряда разработки Microsoft Windows.*  
  
## <a name="see-also"></a>См. также  
 [Рекомендации по проектированию на основе Framework](../../../docs/standard/design-guidelines/index.md)  
 [Правила именования](../../../docs/standard/design-guidelines/naming-guidelines.md)
