---
title: '&lt;sectionGroup&gt; elemento per &lt;configSections&gt;'
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/sectionGroup
helpviewer_keywords:
- sectionGroup Element
- <sectionGroup> Element
ms.assetid: 6c27f9e2-809c-4bc9-aca9-72f90360e7a3
author: guardrex
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5c5c040a322c38da319f2e964519f94d761327e0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="sectiongroup-element-for-configsections"></a><span data-ttu-id="8d4a0-102">\<sectionGroup > elemento per \<configSections ></span><span class="sxs-lookup"><span data-stu-id="8d4a0-102">\<sectionGroup> element for \<configSections></span></span>

<span data-ttu-id="8d4a0-103">Definisce uno spazio dei nomi per le sezioni di configurazione.</span><span class="sxs-lookup"><span data-stu-id="8d4a0-103">Defines a namespace for configuration sections.</span></span>

<span data-ttu-id="8d4a0-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="8d4a0-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="8d4a0-105">&nbsp;&nbsp;[**\<configSections >**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="8d4a0-105">&nbsp;&nbsp;[**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="8d4a0-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<sectionGroup >**</span><span class="sxs-lookup"><span data-stu-id="8d4a0-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<sectionGroup>**</span></span>

## <a name="syntax"></a><span data-ttu-id="8d4a0-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8d4a0-107">Syntax</span></span>

```xml
<sectionGroup name="section group name">
  <!-- Configuration sections -->
</sectionGroup>
```

## <a name="attribute"></a><span data-ttu-id="8d4a0-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="8d4a0-108">Attribute</span></span>

|           | <span data-ttu-id="8d4a0-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8d4a0-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="8d4a0-110">**name**</span><span class="sxs-lookup"><span data-stu-id="8d4a0-110">**name**</span></span>  | <span data-ttu-id="8d4a0-111">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="8d4a0-111">Required attribute.</span></span><br><br><span data-ttu-id="8d4a0-112">Specifica il nome del gruppo di sezioni a cui che si sta definendo.</span><span class="sxs-lookup"><span data-stu-id="8d4a0-112">Specifies the name of the section group you are defining.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="8d4a0-113">Elemento padre</span><span class="sxs-lookup"><span data-stu-id="8d4a0-113">Parent element</span></span>

|     | <span data-ttu-id="8d4a0-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8d4a0-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="8d4a0-115">**\<configSections >** elemento</span><span class="sxs-lookup"><span data-stu-id="8d4a0-115">**\<configSections>** Element</span></span>](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) | <span data-ttu-id="8d4a0-116">Contiene le dichiarazioni dello spazio dei nomi e di sezione di configurazione.</span><span class="sxs-lookup"><span data-stu-id="8d4a0-116">Contains configuration section and namespace declarations.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="8d4a0-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="8d4a0-117">Child elements</span></span>

|     | <span data-ttu-id="8d4a0-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8d4a0-118">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="8d4a0-119">**\<sezione >**</span><span class="sxs-lookup"><span data-stu-id="8d4a0-119">**\<section>**</span></span>](~/docs/framework/configure-apps/file-schema/section-element.md) | <span data-ttu-id="8d4a0-120">Contiene una dichiarazione di sezione di configurazione.</span><span class="sxs-lookup"><span data-stu-id="8d4a0-120">Contains a configuration section declaration.</span></span> |

## <a name="remarks"></a><span data-ttu-id="8d4a0-121">Note</span><span class="sxs-lookup"><span data-stu-id="8d4a0-121">Remarks</span></span>

<span data-ttu-id="8d4a0-122">La dichiarazione di un gruppo di sezioni, crea un tag di contenitore per le sezioni di configurazione e assicura che non sono presenti conflitti di denominazione con sezioni di configurazione definite da un altro utente.</span><span class="sxs-lookup"><span data-stu-id="8d4a0-122">Declaring a section group creates a container tag for configuration sections and ensures that there are no naming conflicts with configuration sections defined by someone else.</span></span> <span data-ttu-id="8d4a0-123">È possibile annidare  **\<sectionGroup >** elementi all'interno di altro.</span><span class="sxs-lookup"><span data-stu-id="8d4a0-123">You can nest **\<sectionGroup>** elements within each other.</span></span>

## <a name="example"></a><span data-ttu-id="8d4a0-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="8d4a0-124">Example</span></span>

<span data-ttu-id="8d4a0-125">Nell'esempio seguente viene illustrato come dichiarare un gruppo di sezioni e dichiarare sezioni all'interno di un gruppo di sezioni:</span><span class="sxs-lookup"><span data-stu-id="8d4a0-125">The following example shows how to declare a section group and declare sections within a section group:</span></span>

```xml
<configuration>
  <configSections>
    <sectionGroup name="mySectionGroup">
      <section name="mySection"
               type="System.Configuration.NameValueSectionHandler,System" />
    </sectionGroup>
  </configSections>
  <mySectionGroup>
    <mySection>
      <add key="key1" value="value1" />
    </mySection>
  </mySectionGroup>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="8d4a0-126">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="8d4a0-126">Configuration file</span></span>

<span data-ttu-id="8d4a0-127">Questo elemento può essere usato nel file di configurazione dell'applicazione, i file di configurazione macchina (*Machine. config*), e *Web. config* file che non sono a livello di directory dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="8d4a0-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="8d4a0-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8d4a0-128">See also</span></span>

[<span data-ttu-id="8d4a0-129">Schema di file di configurazione per .NET Framework</span><span class="sxs-lookup"><span data-stu-id="8d4a0-129">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)