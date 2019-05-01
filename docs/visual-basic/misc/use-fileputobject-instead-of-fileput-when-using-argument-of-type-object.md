---
title: При использовании аргумента с типом Object применяйте FilePutObject вместо FilePut
ms.date: 07/20/2015
f1_keywords:
- vbrUseFilePutObject
ms.assetid: d207b9b7-5898-4c13-8b03-9feefac5f726
ms.openlocfilehash: 3d793151905c61ee12eccdfdb5e9567a4924bb35
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62022523"
---
# <a name="use-fileputobject-instead-of-fileput-when-using-argument-of-type-object"></a>При использовании аргумента с типом Object применяйте FilePutObject вместо FilePut
Метод `FilePut` включает аргумент типа `Object`. Чтобы избежать неоднозначности, следует использовать`FilePutObject` вместо `FilePut` .  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
- Замените `FilePut` объектом `FilePutObject`.  
  
- Приведите аргумент `Object` к более конкретному типу.  
  
- Используйте функциональность объекта `My.Computer.FileSystem` .  
  
## <a name="see-also"></a>См. также

- [My.Computer.FileSystem](xref:Microsoft.VisualBasic.FileIO.FileSystem)
- [My.Computer.FileSystem.WriteAllBytes](xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.WriteAllBytes%2A)
