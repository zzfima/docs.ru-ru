---
title: Объект My.Resources (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- My.Resources
- My.Resources.MyResources.ResourceManager
- My.Resources.MyResources.Culture
helpviewer_keywords:
- My.Resources object
ms.assetid: 34c3f2dc-7b87-432c-9d5f-17ea666bb266
ms.openlocfilehash: 41b6eaa39abfab6cda943162c5c10d1cbeaa9e49
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2018
ms.locfileid: "45595179"
---
# <a name="myresources-object"></a>Объект My.Resources
Предоставляет свойства и классы для доступа к ресурсам приложения.  
  
## <a name="remarks"></a>Примечания  
 `My.Resources` Объект предоставляет доступ к ресурсам приложения и позволяет динамически извлечь ресурсы для приложения. Дополнительные сведения см. в разделе [управлении ресурсами приложения (.NET)](/visualstudio/ide/managing-application-resources-dotnet).  
  
 `My.Resources` Объект предоставляет только глобальные ресурсы. Она предоставляет доступ к файлам ресурсов, связанных с формами. Доступ к ресурсам формы необходимо из формы.  
  
 Получить доступ к файлам ресурсов, связанные с языком и региональными параметрами приложения из `My.Resources` объекта. По умолчанию `My.Resources` объект ищет ресурсы из файла ресурсов, соответствующий язык и региональные параметры в <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.UICulture%2A> свойство. Тем не менее возможность переопределить это поведение и указать определенного языка и региональных параметров для использования для ресурсов. Дополнительные сведения см. в разделе [Ресурсы в приложениях для настольных систем](../../../framework/resources/index.md).  
  
## <a name="properties"></a>Свойства  
 Свойства `My.Resources` объект предоставлять доступ только для чтения к ресурсам приложения. Чтобы добавить или удалить ресурсы, используйте **конструктор проектов**. Можно получить доступ к ресурсам, добавленные с помощью **конструктор проектов** с помощью `My.Resources.``resourceName`.  
  
 Можно также добавить или удалить файлы ресурсов, выбрав проект в **обозревателе решений** и щелкнув **Добавление нового элемента** или **добавить существующий элемент** из  **Проект** меню. Ресурсы, добавленные таким образом, с помощью доступны `My.Resources.``resourceFileName`.`resourceName`.  
  
 Каждый ресурс имеет имя, категорию и значение, и эти параметры ресурсов определяют, как свойство для доступа к ресурсу, отображается в `My.Resources` объекта. Для ресурсов, добавленных в **конструктор проектов**:  
  
-   Имя определяет имя свойства,  
  
-   Данные ресурсов является значением свойства,  
  
-   Категория определяет тип свойства:  
  
|Категория|Тип данных свойства|  
|---|---|  
|**Строки**|[String](../../../visual-basic/language-reference/data-types/string-data-type.md)|  
|**Изображения**|<xref:System.Drawing.Bitmap>|  
|**Значки**|<xref:System.Drawing.Icon>|  
|**Звук**|<xref:System.IO.UnmanagedMemoryStream><br /><br /> <xref:System.IO.UnmanagedMemoryStream> Класс является производным от <xref:System.IO.Stream> класса, чтобы его можно использовать с методами, которые принимают потоки, например <xref:Microsoft.VisualBasic.Devices.Audio.Play%2A> метод.|  
|**Файлы**|-   [Строка](../../../visual-basic/language-reference/data-types/string-data-type.md) для текстовых файлов.<br />-   <xref:System.Drawing.Bitmap> для файлов изображений.<br />-   <xref:System.Drawing.Icon> для файлов значков.<br />-   <xref:System.IO.UnmanagedMemoryStream> для звуковые файлы.|  
|**Другое**|Определяются данными в конструкторе **тип** столбца.|  
  
## <a name="classes"></a>Классы  
 `My.Resources` Объект представляет каждый файл ресурсов как класс с общими свойствами. Имя класса — совпадает с именем файла ресурсов. Как описано в предыдущем разделе, ресурсы в файле ресурсов представляются как свойства в классе.  
  
## <a name="example"></a>Пример  
 В этом примере заголовок формы устанавливается строковый ресурс с именем `Form1Title` в файл ресурсов приложения. Для работы этого примера приложение должно иметь строку с именем `Form1Title` в файле ресурсов.  
  
 [!code-vb[VbVbalrMyResources#1](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_1.vb)]  
  
## <a name="example"></a>Пример  
 В этом примере задает значок формы на значок с именем `Form1Icon` , хранится в файле ресурсов приложения. Для работы этого примера приложение должно иметь значок с именем `Form1Icon` в файле ресурсов.  
  
 [!code-vb[VbVbalrMyResources#2](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_2.vb)]  
  
## <a name="example"></a>Пример  
 В этом примере задает фоновое изображение формы на ресурс образа с именем `Form1Background`, который находится в файле ресурсов приложения. Для работы этого примера приложение должно иметь ресурс изображения с именем `Form1Background` в файле ресурсов.  
  
 [!code-vb[VbVbalrMyResources#3](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_3.vb)]  
  
## <a name="example"></a>Пример  
 В этом примере воспроизводится звук, который хранится в виде звукового ресурса с именем `Form1Greeting` в файл ресурсов приложения. Для работы этого примера приложение должно иметь звукового ресурса с именем `Form1Greeting` в файле ресурсов. `My.Computer.Audio.Play` Метод доступен только для приложений Windows Forms.  
  
 [!code-vb[VbVbalrMyResources#4](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_4.vb)]  
  
## <a name="example"></a>Пример  
 В этом примере извлекается французскую версию строковый ресурс приложения. Ресурс называется `Message`. Чтобы изменить язык и региональные параметры, `My.Resources` использует объект, в примере используется <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.ChangeUICulture%2A>.  
  
 Для работы этого примера приложение должно иметь строку с именем `Message` в его ресурсе файл и приложение должны иметь версию файла ресурсов, Resources.fr-FR.resx французского языка. Если приложение не поддерживает версию файла ресурсов, французского языка `My.Resource` объект извлекает ресурс из файла ресурсов культуры по умолчанию.  
  
 [!code-vb[VbVbalrMyResources#10](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_5.vb)]  
  
## <a name="see-also"></a>См. также  
 [Управление ресурсами приложения (.NET)](/visualstudio/ide/managing-application-resources-dotnet)  
 [Ресурсы в приложениях для настольных систем](../../../framework/resources/index.md)  

