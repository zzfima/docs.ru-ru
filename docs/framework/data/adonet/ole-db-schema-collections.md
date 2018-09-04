---
title: Коллекции схемы OLE DB
ms.date: 03/30/2017
ms.assetid: 6380c36b-658e-4d67-91e8-7131ef4a7c2c
ms.openlocfilehash: 1ab6426875b73b400a59b7e4cf155615d7472d05
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43514493"
---
# <a name="ole-db-schema-collections"></a><span data-ttu-id="a04e4-102">Коллекции схемы OLE DB</span><span class="sxs-lookup"><span data-stu-id="a04e4-102">OLE DB Schema Collections</span></span>
<span data-ttu-id="a04e4-103">В данном разделе рассматривается поддержка коллекций схем для поставщиков OLE DB для Microsoft SQL Server, Oracle и Microsoft Jet.</span><span class="sxs-lookup"><span data-stu-id="a04e4-103">This section discusses schema collection support for the OLE DB providers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-ole-db-provider"></a><span data-ttu-id="a04e4-104">Поставщик OLE DB для Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="a04e4-104">Microsoft SQL Server OLE DB Provider</span></span>  
 <span data-ttu-id="a04e4-105">Драйвер Microsoft SQL Server OLE DB поддерживает следующие специальные коллекции схем в дополнение к общим коллекциям.</span><span class="sxs-lookup"><span data-stu-id="a04e4-105">The Microsoft SQL Server OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="a04e4-106">Таблицы</span><span class="sxs-lookup"><span data-stu-id="a04e4-106">Tables</span></span>  
  
-   <span data-ttu-id="a04e4-107">Столбцы</span><span class="sxs-lookup"><span data-stu-id="a04e4-107">Columns</span></span>  
  
-   <span data-ttu-id="a04e4-108">Процедуры</span><span class="sxs-lookup"><span data-stu-id="a04e4-108">Procedures</span></span>  
  
-   <span data-ttu-id="a04e4-109">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="a04e4-109">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="a04e4-110">Catalog</span><span class="sxs-lookup"><span data-stu-id="a04e4-110">Catalog</span></span>  
  
-   <span data-ttu-id="a04e4-111">Indexes</span><span class="sxs-lookup"><span data-stu-id="a04e4-111">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="a04e4-112">Таблицы</span><span class="sxs-lookup"><span data-stu-id="a04e4-112">Tables</span></span>  
  
|<span data-ttu-id="a04e4-113">ColumnName</span><span class="sxs-lookup"><span data-stu-id="a04e4-113">ColumnName</span></span>|<span data-ttu-id="a04e4-114">DataType</span><span class="sxs-lookup"><span data-stu-id="a04e4-114">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="a04e4-115">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="a04e4-115">TABLE_CATALOG</span></span>|<span data-ttu-id="a04e4-116">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-116">String</span></span>|  
|<span data-ttu-id="a04e4-117">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="a04e4-117">TABLE_SCHEMA</span></span>|<span data-ttu-id="a04e4-118">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-118">String</span></span>|  
|<span data-ttu-id="a04e4-119">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="a04e4-119">TABLE_NAME</span></span>|<span data-ttu-id="a04e4-120">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-120">String</span></span>|  
|<span data-ttu-id="a04e4-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="a04e4-121">TABLE_TYPE</span></span>|<span data-ttu-id="a04e4-122">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-122">String</span></span>|  
|<span data-ttu-id="a04e4-123">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="a04e4-123">TABLE_GUID</span></span>|<span data-ttu-id="a04e4-124">Guid</span><span class="sxs-lookup"><span data-stu-id="a04e4-124">Guid</span></span>|  
|<span data-ttu-id="a04e4-125">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a04e4-125">DESCRIPTION</span></span>|<span data-ttu-id="a04e4-126">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-126">String</span></span>|  
|<span data-ttu-id="a04e4-127">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="a04e4-127">TABLE_PROPID</span></span>|<span data-ttu-id="a04e4-128">Int64</span><span class="sxs-lookup"><span data-stu-id="a04e4-128">Int64</span></span>|  
|<span data-ttu-id="a04e4-129">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="a04e4-129">DATE_CREATED</span></span>|<span data-ttu-id="a04e4-130">DateTime</span><span class="sxs-lookup"><span data-stu-id="a04e4-130">DateTime</span></span>|  
|<span data-ttu-id="a04e4-131">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="a04e4-131">DATE_MODIFIED</span></span>|<span data-ttu-id="a04e4-132">DateTime</span><span class="sxs-lookup"><span data-stu-id="a04e4-132">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="a04e4-133">Столбцы</span><span class="sxs-lookup"><span data-stu-id="a04e4-133">Columns</span></span>  
  
|<span data-ttu-id="a04e4-134">ColumnName</span><span class="sxs-lookup"><span data-stu-id="a04e4-134">ColumnName</span></span>|<span data-ttu-id="a04e4-135">DataType</span><span class="sxs-lookup"><span data-stu-id="a04e4-135">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="a04e4-136">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="a04e4-136">TABLE_CATALOG</span></span>|<span data-ttu-id="a04e4-137">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-137">String</span></span>|  
|<span data-ttu-id="a04e4-138">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="a04e4-138">TABLE_SCHEMA</span></span>|<span data-ttu-id="a04e4-139">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-139">String</span></span>|  
|<span data-ttu-id="a04e4-140">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="a04e4-140">TABLE_NAME</span></span>|<span data-ttu-id="a04e4-141">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-141">String</span></span>|  
|<span data-ttu-id="a04e4-142">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="a04e4-142">COLUMN_NAME</span></span>|<span data-ttu-id="a04e4-143">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-143">String</span></span>|  
|<span data-ttu-id="a04e4-144">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="a04e4-144">COLUMN_GUID</span></span>|<span data-ttu-id="a04e4-145">Guid</span><span class="sxs-lookup"><span data-stu-id="a04e4-145">Guid</span></span>|  
|<span data-ttu-id="a04e4-146">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="a04e4-146">COLUMN_PROPID</span></span>|<span data-ttu-id="a04e4-147">Int64</span><span class="sxs-lookup"><span data-stu-id="a04e4-147">Int64</span></span>|  
|<span data-ttu-id="a04e4-148">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="a04e4-148">ORDINAL_POSITION</span></span>|<span data-ttu-id="a04e4-149">Int64</span><span class="sxs-lookup"><span data-stu-id="a04e4-149">Int64</span></span>|  
|<span data-ttu-id="a04e4-150">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="a04e4-150">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="a04e4-151">Boolean</span><span class="sxs-lookup"><span data-stu-id="a04e4-151">Boolean</span></span>|  
|<span data-ttu-id="a04e4-152">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="a04e4-152">COLUMN_DEFAULT</span></span>|<span data-ttu-id="a04e4-153">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-153">String</span></span>|  
|<span data-ttu-id="a04e4-154">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="a04e4-154">COLUMN_FLAGS</span></span>|<span data-ttu-id="a04e4-155">Int64</span><span class="sxs-lookup"><span data-stu-id="a04e4-155">Int64</span></span>|  
|<span data-ttu-id="a04e4-156">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="a04e4-156">IS_NULLABLE</span></span>|<span data-ttu-id="a04e4-157">Boolean</span><span class="sxs-lookup"><span data-stu-id="a04e4-157">Boolean</span></span>|  
|<span data-ttu-id="a04e4-158">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="a04e4-158">DATA_TYPE</span></span>|<span data-ttu-id="a04e4-159">Int32</span><span class="sxs-lookup"><span data-stu-id="a04e4-159">Int32</span></span>|  
|<span data-ttu-id="a04e4-160">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="a04e4-160">TYPE_GUID</span></span>|<span data-ttu-id="a04e4-161">Guid</span><span class="sxs-lookup"><span data-stu-id="a04e4-161">Guid</span></span>|  
|<span data-ttu-id="a04e4-162">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="a04e4-162">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="a04e4-163">Int64</span><span class="sxs-lookup"><span data-stu-id="a04e4-163">Int64</span></span>|  
|<span data-ttu-id="a04e4-164">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="a04e4-164">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="a04e4-165">Int64</span><span class="sxs-lookup"><span data-stu-id="a04e4-165">Int64</span></span>|  
|<span data-ttu-id="a04e4-166">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="a04e4-166">NUMERIC_PRECISION</span></span>|<span data-ttu-id="a04e4-167">Int32</span><span class="sxs-lookup"><span data-stu-id="a04e4-167">Int32</span></span>|  
|<span data-ttu-id="a04e4-168">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="a04e4-168">NUMERIC_SCALE</span></span>|<span data-ttu-id="a04e4-169">Int16</span><span class="sxs-lookup"><span data-stu-id="a04e4-169">Int16</span></span>|  
|<span data-ttu-id="a04e4-170">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="a04e4-170">DATETIME_PRECISION</span></span>|<span data-ttu-id="a04e4-171">Int64</span><span class="sxs-lookup"><span data-stu-id="a04e4-171">Int64</span></span>|  
|<span data-ttu-id="a04e4-172">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="a04e4-172">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="a04e4-173">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-173">String</span></span>|  
|<span data-ttu-id="a04e4-174">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="a04e4-174">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="a04e4-175">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-175">String</span></span>|  
|<span data-ttu-id="a04e4-176">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="a04e4-176">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="a04e4-177">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-177">String</span></span>|  
|<span data-ttu-id="a04e4-178">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="a04e4-178">COLLATION_CATALOG</span></span>|<span data-ttu-id="a04e4-179">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-179">String</span></span>|  
|<span data-ttu-id="a04e4-180">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="a04e4-180">COLLATION_SCHEMA</span></span>|<span data-ttu-id="a04e4-181">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-181">String</span></span>|  
|<span data-ttu-id="a04e4-182">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="a04e4-182">COLLATION_NAME</span></span>|<span data-ttu-id="a04e4-183">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-183">String</span></span>|  
|<span data-ttu-id="a04e4-184">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="a04e4-184">DOMAIN_CATALOG</span></span>|<span data-ttu-id="a04e4-185">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-185">String</span></span>|  
|<span data-ttu-id="a04e4-186">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="a04e4-186">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="a04e4-187">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-187">String</span></span>|  
|<span data-ttu-id="a04e4-188">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="a04e4-188">DOMAIN_NAME</span></span>|<span data-ttu-id="a04e4-189">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-189">String</span></span>|  
|<span data-ttu-id="a04e4-190">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a04e4-190">DESCRIPTION</span></span>|<span data-ttu-id="a04e4-191">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-191">String</span></span>|  
|<span data-ttu-id="a04e4-192">COLUMN_LCID</span><span class="sxs-lookup"><span data-stu-id="a04e4-192">COLUMN_LCID</span></span>|<span data-ttu-id="a04e4-193">Int32</span><span class="sxs-lookup"><span data-stu-id="a04e4-193">Int32</span></span>|  
|<span data-ttu-id="a04e4-194">COLUMN_COMPFLAGS</span><span class="sxs-lookup"><span data-stu-id="a04e4-194">COLUMN_COMPFLAGS</span></span>|<span data-ttu-id="a04e4-195">Int32</span><span class="sxs-lookup"><span data-stu-id="a04e4-195">Int32</span></span>|  
|<span data-ttu-id="a04e4-196">COLUMN_SORTID</span><span class="sxs-lookup"><span data-stu-id="a04e4-196">COLUMN_SORTID</span></span>|<span data-ttu-id="a04e4-197">Int32</span><span class="sxs-lookup"><span data-stu-id="a04e4-197">Int32</span></span>|  
|<span data-ttu-id="a04e4-198">COLUMN_TDSCOLLATION</span><span class="sxs-lookup"><span data-stu-id="a04e4-198">COLUMN_TDSCOLLATION</span></span>|<span data-ttu-id="a04e4-199">Byte[]</span><span class="sxs-lookup"><span data-stu-id="a04e4-199">Byte[]</span></span>|  
|<span data-ttu-id="a04e4-200">IS_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="a04e4-200">IS_COMPUTED</span></span>|<span data-ttu-id="a04e4-201">Boolean</span><span class="sxs-lookup"><span data-stu-id="a04e4-201">Boolean</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="a04e4-202">Процедуры</span><span class="sxs-lookup"><span data-stu-id="a04e4-202">Procedures</span></span>  
  
|<span data-ttu-id="a04e4-203">ColumnName</span><span class="sxs-lookup"><span data-stu-id="a04e4-203">ColumnName</span></span>|<span data-ttu-id="a04e4-204">DataType</span><span class="sxs-lookup"><span data-stu-id="a04e4-204">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="a04e4-205">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="a04e4-205">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="a04e4-206">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-206">String</span></span>|  
|<span data-ttu-id="a04e4-207">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="a04e4-207">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="a04e4-208">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-208">String</span></span>|  
|<span data-ttu-id="a04e4-209">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="a04e4-209">PROCEDURE_NAME</span></span>|<span data-ttu-id="a04e4-210">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-210">String</span></span>|  
|<span data-ttu-id="a04e4-211">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="a04e4-211">PROCEDURE_TYPE</span></span>|<span data-ttu-id="a04e4-212">Int16</span><span class="sxs-lookup"><span data-stu-id="a04e4-212">Int16</span></span>|  
|<span data-ttu-id="a04e4-213">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="a04e4-213">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="a04e4-214">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-214">String</span></span>|  
|<span data-ttu-id="a04e4-215">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a04e4-215">DESCRIPTION</span></span>|<span data-ttu-id="a04e4-216">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-216">String</span></span>|  
|<span data-ttu-id="a04e4-217">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="a04e4-217">DATE_CREATED</span></span>|<span data-ttu-id="a04e4-218">DateTime</span><span class="sxs-lookup"><span data-stu-id="a04e4-218">DateTime</span></span>|  
|<span data-ttu-id="a04e4-219">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="a04e4-219">DATE_MODIFIED</span></span>|<span data-ttu-id="a04e4-220">DateTime</span><span class="sxs-lookup"><span data-stu-id="a04e4-220">DateTime</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="a04e4-221">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="a04e4-221">ProcedureParameters</span></span>  
  
|<span data-ttu-id="a04e4-222">ColumnName</span><span class="sxs-lookup"><span data-stu-id="a04e4-222">ColumnName</span></span>|<span data-ttu-id="a04e4-223">DataType</span><span class="sxs-lookup"><span data-stu-id="a04e4-223">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="a04e4-224">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="a04e4-224">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="a04e4-225">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-225">String</span></span>|  
|<span data-ttu-id="a04e4-226">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="a04e4-226">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="a04e4-227">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-227">String</span></span>|  
|<span data-ttu-id="a04e4-228">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="a04e4-228">PROCEDURE_NAME</span></span>|<span data-ttu-id="a04e4-229">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-229">String</span></span>|  
|<span data-ttu-id="a04e4-230">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="a04e4-230">PARAMETER_NAME</span></span>|<span data-ttu-id="a04e4-231">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-231">String</span></span>|  
|<span data-ttu-id="a04e4-232">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="a04e4-232">ORDINAL_POSITION</span></span>|<span data-ttu-id="a04e4-233">Int32</span><span class="sxs-lookup"><span data-stu-id="a04e4-233">Int32</span></span>|  
|<span data-ttu-id="a04e4-234">PARAMETER_TYPE</span><span class="sxs-lookup"><span data-stu-id="a04e4-234">PARAMETER_TYPE</span></span>|<span data-ttu-id="a04e4-235">Int32</span><span class="sxs-lookup"><span data-stu-id="a04e4-235">Int32</span></span>|  
|<span data-ttu-id="a04e4-236">PARAMETER_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="a04e4-236">PARAMETER_HASDEFAULT</span></span>|<span data-ttu-id="a04e4-237">Boolean</span><span class="sxs-lookup"><span data-stu-id="a04e4-237">Boolean</span></span>|  
|<span data-ttu-id="a04e4-238">PARAMETER_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="a04e4-238">PARAMETER_DEFAULT</span></span>|<span data-ttu-id="a04e4-239">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-239">String</span></span>|  
|<span data-ttu-id="a04e4-240">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="a04e4-240">IS_NULLABLE</span></span>|<span data-ttu-id="a04e4-241">Boolean</span><span class="sxs-lookup"><span data-stu-id="a04e4-241">Boolean</span></span>|  
|<span data-ttu-id="a04e4-242">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="a04e4-242">DATA_TYPE</span></span>|<span data-ttu-id="a04e4-243">Int32</span><span class="sxs-lookup"><span data-stu-id="a04e4-243">Int32</span></span>|  
|<span data-ttu-id="a04e4-244">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="a04e4-244">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="a04e4-245">Int64</span><span class="sxs-lookup"><span data-stu-id="a04e4-245">Int64</span></span>|  
|<span data-ttu-id="a04e4-246">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="a04e4-246">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="a04e4-247">Int64</span><span class="sxs-lookup"><span data-stu-id="a04e4-247">Int64</span></span>|  
|<span data-ttu-id="a04e4-248">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="a04e4-248">NUMERIC_PRECISION</span></span>|<span data-ttu-id="a04e4-249">Int32</span><span class="sxs-lookup"><span data-stu-id="a04e4-249">Int32</span></span>|  
|<span data-ttu-id="a04e4-250">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="a04e4-250">NUMERIC_SCALE</span></span>|<span data-ttu-id="a04e4-251">Int16</span><span class="sxs-lookup"><span data-stu-id="a04e4-251">Int16</span></span>|  
|<span data-ttu-id="a04e4-252">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a04e4-252">DESCRIPTION</span></span>|<span data-ttu-id="a04e4-253">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-253">String</span></span>|  
|<span data-ttu-id="a04e4-254">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="a04e4-254">TYPE_NAME</span></span>|<span data-ttu-id="a04e4-255">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-255">String</span></span>|  
|<span data-ttu-id="a04e4-256">LOCAL_TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="a04e4-256">LOCAL_TYPE_NAME</span></span>|<span data-ttu-id="a04e4-257">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-257">String</span></span>|  
  
### <a name="catalog"></a><span data-ttu-id="a04e4-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="a04e4-258">Catalog</span></span>  
  
|<span data-ttu-id="a04e4-259">ColumnName</span><span class="sxs-lookup"><span data-stu-id="a04e4-259">ColumnName</span></span>|<span data-ttu-id="a04e4-260">DataType</span><span class="sxs-lookup"><span data-stu-id="a04e4-260">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="a04e4-261">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="a04e4-261">CATALOG_NAME</span></span>|<span data-ttu-id="a04e4-262">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-262">String</span></span>|  
|<span data-ttu-id="a04e4-263">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a04e4-263">DESCRIPTION</span></span>|<span data-ttu-id="a04e4-264">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-264">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="a04e4-265">Indexes</span><span class="sxs-lookup"><span data-stu-id="a04e4-265">Indexes</span></span>  
  
|<span data-ttu-id="a04e4-266">ColumnName</span><span class="sxs-lookup"><span data-stu-id="a04e4-266">ColumnName</span></span>|<span data-ttu-id="a04e4-267">DataType</span><span class="sxs-lookup"><span data-stu-id="a04e4-267">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="a04e4-268">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="a04e4-268">TABLE_CATALOG</span></span>|<span data-ttu-id="a04e4-269">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-269">String</span></span>|  
|<span data-ttu-id="a04e4-270">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="a04e4-270">TABLE_SCHEMA</span></span>|<span data-ttu-id="a04e4-271">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-271">String</span></span>|  
|<span data-ttu-id="a04e4-272">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="a04e4-272">TABLE_NAME</span></span>|<span data-ttu-id="a04e4-273">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-273">String</span></span>|  
|<span data-ttu-id="a04e4-274">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="a04e4-274">INDEX_CATALOG</span></span>|<span data-ttu-id="a04e4-275">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-275">String</span></span>|  
|<span data-ttu-id="a04e4-276">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="a04e4-276">INDEX_SCHEMA</span></span>|<span data-ttu-id="a04e4-277">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-277">String</span></span>|  
|<span data-ttu-id="a04e4-278">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="a04e4-278">INDEX_NAME</span></span>|<span data-ttu-id="a04e4-279">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-279">String</span></span>|  
|<span data-ttu-id="a04e4-280">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="a04e4-280">PRIMARY_KEY</span></span>|<span data-ttu-id="a04e4-281">Boolean</span><span class="sxs-lookup"><span data-stu-id="a04e4-281">Boolean</span></span>|  
|<span data-ttu-id="a04e4-282">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="a04e4-282">UNIQUE</span></span>|<span data-ttu-id="a04e4-283">Boolean</span><span class="sxs-lookup"><span data-stu-id="a04e4-283">Boolean</span></span>|  
|<span data-ttu-id="a04e4-284">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="a04e4-284">CLUSTERED</span></span>|<span data-ttu-id="a04e4-285">Boolean</span><span class="sxs-lookup"><span data-stu-id="a04e4-285">Boolean</span></span>|  
|<span data-ttu-id="a04e4-286">TYPE</span><span class="sxs-lookup"><span data-stu-id="a04e4-286">TYPE</span></span>|<span data-ttu-id="a04e4-287">Int32</span><span class="sxs-lookup"><span data-stu-id="a04e4-287">Int32</span></span>|  
|<span data-ttu-id="a04e4-288">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="a04e4-288">FILL_FACTOR</span></span>|<span data-ttu-id="a04e4-289">Int32</span><span class="sxs-lookup"><span data-stu-id="a04e4-289">Int32</span></span>|  
|<span data-ttu-id="a04e4-290">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="a04e4-290">INITIAL_SIZE</span></span>|<span data-ttu-id="a04e4-291">Int32</span><span class="sxs-lookup"><span data-stu-id="a04e4-291">Int32</span></span>|  
|<span data-ttu-id="a04e4-292">NULLS</span><span class="sxs-lookup"><span data-stu-id="a04e4-292">NULLS</span></span>|<span data-ttu-id="a04e4-293">Int32</span><span class="sxs-lookup"><span data-stu-id="a04e4-293">Int32</span></span>|  
|<span data-ttu-id="a04e4-294">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="a04e4-294">SORT_BOOKMARKS</span></span>|<span data-ttu-id="a04e4-295">Boolean</span><span class="sxs-lookup"><span data-stu-id="a04e4-295">Boolean</span></span>|  
|<span data-ttu-id="a04e4-296">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="a04e4-296">AUTO_UPDATE</span></span>|<span data-ttu-id="a04e4-297">Boolean</span><span class="sxs-lookup"><span data-stu-id="a04e4-297">Boolean</span></span>|  
|<span data-ttu-id="a04e4-298">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="a04e4-298">NULL_COLLATION</span></span>|<span data-ttu-id="a04e4-299">Int32</span><span class="sxs-lookup"><span data-stu-id="a04e4-299">Int32</span></span>|  
|<span data-ttu-id="a04e4-300">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="a04e4-300">ORDINAL_POSITION</span></span>|<span data-ttu-id="a04e4-301">Int64</span><span class="sxs-lookup"><span data-stu-id="a04e4-301">Int64</span></span>|  
|<span data-ttu-id="a04e4-302">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="a04e4-302">COLUMN_NAME</span></span>|<span data-ttu-id="a04e4-303">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-303">String</span></span>|  
|<span data-ttu-id="a04e4-304">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="a04e4-304">COLUMN_GUID</span></span>|<span data-ttu-id="a04e4-305">Guid</span><span class="sxs-lookup"><span data-stu-id="a04e4-305">Guid</span></span>|  
|<span data-ttu-id="a04e4-306">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="a04e4-306">COLUMN_PROPID</span></span>|<span data-ttu-id="a04e4-307">Int64</span><span class="sxs-lookup"><span data-stu-id="a04e4-307">Int64</span></span>|  
|<span data-ttu-id="a04e4-308">COLLATION</span><span class="sxs-lookup"><span data-stu-id="a04e4-308">COLLATION</span></span>|<span data-ttu-id="a04e4-309">Int16</span><span class="sxs-lookup"><span data-stu-id="a04e4-309">Int16</span></span>|  
|<span data-ttu-id="a04e4-310">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="a04e4-310">CARDINALITY</span></span>|<span data-ttu-id="a04e4-311">Десятичное число</span><span class="sxs-lookup"><span data-stu-id="a04e4-311">Decimal</span></span>|  
|<span data-ttu-id="a04e4-312">PAGES</span><span class="sxs-lookup"><span data-stu-id="a04e4-312">PAGES</span></span>|<span data-ttu-id="a04e4-313">Int32</span><span class="sxs-lookup"><span data-stu-id="a04e4-313">Int32</span></span>|  
|<span data-ttu-id="a04e4-314">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="a04e4-314">FILTER_CONDITION</span></span>|<span data-ttu-id="a04e4-315">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-315">String</span></span>|  
|<span data-ttu-id="a04e4-316">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="a04e4-316">INTEGRATED</span></span>|<span data-ttu-id="a04e4-317">Boolean</span><span class="sxs-lookup"><span data-stu-id="a04e4-317">Boolean</span></span>|  
  
## <a name="microsoft-oracle-ole-db-provider"></a><span data-ttu-id="a04e4-318">Поставщик Microsoft OLE DB для Oracle</span><span class="sxs-lookup"><span data-stu-id="a04e4-318">Microsoft Oracle OLE DB Provider</span></span>  
 <span data-ttu-id="a04e4-319">Драйвер OLE DB для Oracle (Майкрософт) поддерживает следующие специальные коллекции схем в дополнение к общим коллекциям.</span><span class="sxs-lookup"><span data-stu-id="a04e4-319">The Microsoft Oracle OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="a04e4-320">Таблицы</span><span class="sxs-lookup"><span data-stu-id="a04e4-320">Tables</span></span>  
  
-   <span data-ttu-id="a04e4-321">Столбцы</span><span class="sxs-lookup"><span data-stu-id="a04e4-321">Columns</span></span>  
  
-   <span data-ttu-id="a04e4-322">Процедуры</span><span class="sxs-lookup"><span data-stu-id="a04e4-322">Procedures</span></span>  
  
-   <span data-ttu-id="a04e4-323">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="a04e4-323">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="a04e4-324">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="a04e4-324">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="a04e4-325">Представления</span><span class="sxs-lookup"><span data-stu-id="a04e4-325">Views</span></span>  
  
-   <span data-ttu-id="a04e4-326">Indexes</span><span class="sxs-lookup"><span data-stu-id="a04e4-326">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="a04e4-327">Таблицы</span><span class="sxs-lookup"><span data-stu-id="a04e4-327">Tables</span></span>  
  
|<span data-ttu-id="a04e4-328">ColumnName</span><span class="sxs-lookup"><span data-stu-id="a04e4-328">ColumnName</span></span>|<span data-ttu-id="a04e4-329">DataType</span><span class="sxs-lookup"><span data-stu-id="a04e4-329">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="a04e4-330">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="a04e4-330">TABLE_CATALOG</span></span>|<span data-ttu-id="a04e4-331">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-331">String</span></span>|  
|<span data-ttu-id="a04e4-332">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="a04e4-332">TABLE_SCHEMA</span></span>|<span data-ttu-id="a04e4-333">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-333">String</span></span>|  
|<span data-ttu-id="a04e4-334">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="a04e4-334">TABLE_NAME</span></span>|<span data-ttu-id="a04e4-335">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-335">String</span></span>|  
|<span data-ttu-id="a04e4-336">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="a04e4-336">TABLE_TYPE</span></span>|<span data-ttu-id="a04e4-337">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-337">String</span></span>|  
|<span data-ttu-id="a04e4-338">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="a04e4-338">TABLE_GUID</span></span>|<span data-ttu-id="a04e4-339">Guid</span><span class="sxs-lookup"><span data-stu-id="a04e4-339">Guid</span></span>|  
|<span data-ttu-id="a04e4-340">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a04e4-340">DESCRIPTION</span></span>|<span data-ttu-id="a04e4-341">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-341">String</span></span>|  
|<span data-ttu-id="a04e4-342">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="a04e4-342">TABLE_PROPID</span></span>|<span data-ttu-id="a04e4-343">Int64</span><span class="sxs-lookup"><span data-stu-id="a04e4-343">Int64</span></span>|  
|<span data-ttu-id="a04e4-344">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="a04e4-344">DATE_CREATED</span></span>|<span data-ttu-id="a04e4-345">DateTime</span><span class="sxs-lookup"><span data-stu-id="a04e4-345">DateTime</span></span>|  
|<span data-ttu-id="a04e4-346">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="a04e4-346">DATE_MODIFIED</span></span>|<span data-ttu-id="a04e4-347">DateTime</span><span class="sxs-lookup"><span data-stu-id="a04e4-347">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="a04e4-348">Столбцы</span><span class="sxs-lookup"><span data-stu-id="a04e4-348">Columns</span></span>  
  
|<span data-ttu-id="a04e4-349">ColumnName</span><span class="sxs-lookup"><span data-stu-id="a04e4-349">ColumnName</span></span>|<span data-ttu-id="a04e4-350">DataType</span><span class="sxs-lookup"><span data-stu-id="a04e4-350">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="a04e4-351">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="a04e4-351">TABLE_CATALOG</span></span>|<span data-ttu-id="a04e4-352">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-352">String</span></span>|  
|<span data-ttu-id="a04e4-353">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="a04e4-353">TABLE_SCHEMA</span></span>|<span data-ttu-id="a04e4-354">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-354">String</span></span>|  
|<span data-ttu-id="a04e4-355">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="a04e4-355">TABLE_NAME</span></span>|<span data-ttu-id="a04e4-356">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-356">String</span></span>|  
|<span data-ttu-id="a04e4-357">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="a04e4-357">COLUMN_NAME</span></span>|<span data-ttu-id="a04e4-358">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-358">String</span></span>|  
|<span data-ttu-id="a04e4-359">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="a04e4-359">COLUMN_GUID</span></span>|<span data-ttu-id="a04e4-360">Guid</span><span class="sxs-lookup"><span data-stu-id="a04e4-360">Guid</span></span>|  
|<span data-ttu-id="a04e4-361">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="a04e4-361">COLUMN_PROPID</span></span>|<span data-ttu-id="a04e4-362">Int64</span><span class="sxs-lookup"><span data-stu-id="a04e4-362">Int64</span></span>|  
|<span data-ttu-id="a04e4-363">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="a04e4-363">ORDINAL_POSITION</span></span>|<span data-ttu-id="a04e4-364">Int64</span><span class="sxs-lookup"><span data-stu-id="a04e4-364">Int64</span></span>|  
|<span data-ttu-id="a04e4-365">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="a04e4-365">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="a04e4-366">Boolean</span><span class="sxs-lookup"><span data-stu-id="a04e4-366">Boolean</span></span>|  
|<span data-ttu-id="a04e4-367">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="a04e4-367">COLUMN_DEFAULT</span></span>|<span data-ttu-id="a04e4-368">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-368">String</span></span>|  
|<span data-ttu-id="a04e4-369">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="a04e4-369">COLUMN_FLAGS</span></span>|<span data-ttu-id="a04e4-370">Int64</span><span class="sxs-lookup"><span data-stu-id="a04e4-370">Int64</span></span>|  
|<span data-ttu-id="a04e4-371">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="a04e4-371">IS_NULLABLE</span></span>|<span data-ttu-id="a04e4-372">Boolean</span><span class="sxs-lookup"><span data-stu-id="a04e4-372">Boolean</span></span>|  
|<span data-ttu-id="a04e4-373">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="a04e4-373">DATA_TYPE</span></span>|<span data-ttu-id="a04e4-374">Int32</span><span class="sxs-lookup"><span data-stu-id="a04e4-374">Int32</span></span>|  
|<span data-ttu-id="a04e4-375">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="a04e4-375">TYPE_GUID</span></span>|<span data-ttu-id="a04e4-376">Guid</span><span class="sxs-lookup"><span data-stu-id="a04e4-376">Guid</span></span>|  
|<span data-ttu-id="a04e4-377">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="a04e4-377">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="a04e4-378">Int64</span><span class="sxs-lookup"><span data-stu-id="a04e4-378">Int64</span></span>|  
|<span data-ttu-id="a04e4-379">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="a04e4-379">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="a04e4-380">Int64</span><span class="sxs-lookup"><span data-stu-id="a04e4-380">Int64</span></span>|  
|<span data-ttu-id="a04e4-381">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="a04e4-381">NUMERIC_PRECISION</span></span>|<span data-ttu-id="a04e4-382">Int32</span><span class="sxs-lookup"><span data-stu-id="a04e4-382">Int32</span></span>|  
|<span data-ttu-id="a04e4-383">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="a04e4-383">NUMERIC_SCALE</span></span>|<span data-ttu-id="a04e4-384">Int16</span><span class="sxs-lookup"><span data-stu-id="a04e4-384">Int16</span></span>|  
|<span data-ttu-id="a04e4-385">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="a04e4-385">DATETIME_PRECISION</span></span>|<span data-ttu-id="a04e4-386">Int64</span><span class="sxs-lookup"><span data-stu-id="a04e4-386">Int64</span></span>|  
|<span data-ttu-id="a04e4-387">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="a04e4-387">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="a04e4-388">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-388">String</span></span>|  
|<span data-ttu-id="a04e4-389">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="a04e4-389">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="a04e4-390">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-390">String</span></span>|  
|<span data-ttu-id="a04e4-391">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="a04e4-391">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="a04e4-392">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-392">String</span></span>|  
|<span data-ttu-id="a04e4-393">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="a04e4-393">COLLATION_CATALOG</span></span>|<span data-ttu-id="a04e4-394">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-394">String</span></span>|  
|<span data-ttu-id="a04e4-395">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="a04e4-395">COLLATION_SCHEMA</span></span>|<span data-ttu-id="a04e4-396">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-396">String</span></span>|  
|<span data-ttu-id="a04e4-397">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="a04e4-397">COLLATION_NAME</span></span>|<span data-ttu-id="a04e4-398">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-398">String</span></span>|  
|<span data-ttu-id="a04e4-399">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="a04e4-399">DOMAIN_CATALOG</span></span>|<span data-ttu-id="a04e4-400">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-400">String</span></span>|  
|<span data-ttu-id="a04e4-401">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="a04e4-401">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="a04e4-402">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-402">String</span></span>|  
|<span data-ttu-id="a04e4-403">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="a04e4-403">DOMAIN_NAME</span></span>|<span data-ttu-id="a04e4-404">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-404">String</span></span>|  
|<span data-ttu-id="a04e4-405">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a04e4-405">DESCRIPTION</span></span>|<span data-ttu-id="a04e4-406">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-406">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="a04e4-407">Процедуры</span><span class="sxs-lookup"><span data-stu-id="a04e4-407">Procedures</span></span>  
  
|<span data-ttu-id="a04e4-408">ColumnName</span><span class="sxs-lookup"><span data-stu-id="a04e4-408">ColumnName</span></span>|<span data-ttu-id="a04e4-409">DataType</span><span class="sxs-lookup"><span data-stu-id="a04e4-409">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="a04e4-410">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="a04e4-410">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="a04e4-411">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-411">String</span></span>|  
|<span data-ttu-id="a04e4-412">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="a04e4-412">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="a04e4-413">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-413">String</span></span>|  
|<span data-ttu-id="a04e4-414">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="a04e4-414">PROCEDURE_NAME</span></span>|<span data-ttu-id="a04e4-415">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-415">String</span></span>|  
|<span data-ttu-id="a04e4-416">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="a04e4-416">PROCEDURE_TYPE</span></span>|<span data-ttu-id="a04e4-417">Int16</span><span class="sxs-lookup"><span data-stu-id="a04e4-417">Int16</span></span>|  
|<span data-ttu-id="a04e4-418">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="a04e4-418">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="a04e4-419">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-419">String</span></span>|  
|<span data-ttu-id="a04e4-420">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a04e4-420">DESCRIPTION</span></span>|<span data-ttu-id="a04e4-421">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-421">String</span></span>|  
|<span data-ttu-id="a04e4-422">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="a04e4-422">DATE_CREATED</span></span>|<span data-ttu-id="a04e4-423">DateTime</span><span class="sxs-lookup"><span data-stu-id="a04e4-423">DateTime</span></span>|  
|<span data-ttu-id="a04e4-424">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="a04e4-424">DATE_MODIFIED</span></span>|<span data-ttu-id="a04e4-425">DateTime</span><span class="sxs-lookup"><span data-stu-id="a04e4-425">DateTime</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="a04e4-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="a04e4-426">ProcedureColumns</span></span>  
  
|<span data-ttu-id="a04e4-427">ColumnName</span><span class="sxs-lookup"><span data-stu-id="a04e4-427">ColumnName</span></span>|<span data-ttu-id="a04e4-428">DataType</span><span class="sxs-lookup"><span data-stu-id="a04e4-428">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="a04e4-429">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="a04e4-429">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="a04e4-430">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-430">String</span></span>|  
|<span data-ttu-id="a04e4-431">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="a04e4-431">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="a04e4-432">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-432">String</span></span>|  
|<span data-ttu-id="a04e4-433">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="a04e4-433">PROCEDURE_NAME</span></span>|<span data-ttu-id="a04e4-434">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-434">String</span></span>|  
|<span data-ttu-id="a04e4-435">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="a04e4-435">COLUMN_NAME</span></span>|<span data-ttu-id="a04e4-436">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-436">String</span></span>|  
|<span data-ttu-id="a04e4-437">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="a04e4-437">COLUMN_GUID</span></span>|<span data-ttu-id="a04e4-438">Guid</span><span class="sxs-lookup"><span data-stu-id="a04e4-438">Guid</span></span>|  
|<span data-ttu-id="a04e4-439">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="a04e4-439">COLUMN_PROPID</span></span>|<span data-ttu-id="a04e4-440">Int64</span><span class="sxs-lookup"><span data-stu-id="a04e4-440">Int64</span></span>|  
|<span data-ttu-id="a04e4-441">ROWSET_NUMBER</span><span class="sxs-lookup"><span data-stu-id="a04e4-441">ROWSET_NUMBER</span></span>|<span data-ttu-id="a04e4-442">Int64</span><span class="sxs-lookup"><span data-stu-id="a04e4-442">Int64</span></span>|  
|<span data-ttu-id="a04e4-443">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="a04e4-443">ORDINAL_POSITION</span></span>|<span data-ttu-id="a04e4-444">Int64</span><span class="sxs-lookup"><span data-stu-id="a04e4-444">Int64</span></span>|  
|<span data-ttu-id="a04e4-445">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="a04e4-445">IS_NULLABLE</span></span>|<span data-ttu-id="a04e4-446">Boolean</span><span class="sxs-lookup"><span data-stu-id="a04e4-446">Boolean</span></span>|  
|<span data-ttu-id="a04e4-447">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="a04e4-447">DATA_TYPE</span></span>|<span data-ttu-id="a04e4-448">Int32</span><span class="sxs-lookup"><span data-stu-id="a04e4-448">Int32</span></span>|  
|<span data-ttu-id="a04e4-449">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="a04e4-449">TYPE_GUID</span></span>|<span data-ttu-id="a04e4-450">Guid</span><span class="sxs-lookup"><span data-stu-id="a04e4-450">Guid</span></span>|  
|<span data-ttu-id="a04e4-451">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="a04e4-451">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="a04e4-452">Int64</span><span class="sxs-lookup"><span data-stu-id="a04e4-452">Int64</span></span>|  
|<span data-ttu-id="a04e4-453">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="a04e4-453">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="a04e4-454">Int64</span><span class="sxs-lookup"><span data-stu-id="a04e4-454">Int64</span></span>|  
|<span data-ttu-id="a04e4-455">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="a04e4-455">NUMERIC_PRECISION</span></span>|<span data-ttu-id="a04e4-456">Int32</span><span class="sxs-lookup"><span data-stu-id="a04e4-456">Int32</span></span>|  
|<span data-ttu-id="a04e4-457">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="a04e4-457">NUMERIC_SCALE</span></span>|<span data-ttu-id="a04e4-458">Int16</span><span class="sxs-lookup"><span data-stu-id="a04e4-458">Int16</span></span>|  
|<span data-ttu-id="a04e4-459">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a04e4-459">DESCRIPTION</span></span>|<span data-ttu-id="a04e4-460">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-460">String</span></span>|  
|<span data-ttu-id="a04e4-461">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="a04e4-461">OVERLOAD</span></span>|<span data-ttu-id="a04e4-462">Int16</span><span class="sxs-lookup"><span data-stu-id="a04e4-462">Int16</span></span>|  
  
### <a name="views"></a><span data-ttu-id="a04e4-463">Представления</span><span class="sxs-lookup"><span data-stu-id="a04e4-463">Views</span></span>  
  
|<span data-ttu-id="a04e4-464">ColumnName</span><span class="sxs-lookup"><span data-stu-id="a04e4-464">ColumnName</span></span>|<span data-ttu-id="a04e4-465">DataType</span><span class="sxs-lookup"><span data-stu-id="a04e4-465">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="a04e4-466">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="a04e4-466">TABLE_CATALOG</span></span>|<span data-ttu-id="a04e4-467">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-467">String</span></span>|  
|<span data-ttu-id="a04e4-468">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="a04e4-468">TABLE_SCHEMA</span></span>|<span data-ttu-id="a04e4-469">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-469">String</span></span>|  
|<span data-ttu-id="a04e4-470">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="a04e4-470">TABLE_NAME</span></span>|<span data-ttu-id="a04e4-471">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-471">String</span></span>|  
|<span data-ttu-id="a04e4-472">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="a04e4-472">VIEW_DEFINITION</span></span>|<span data-ttu-id="a04e4-473">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-473">String</span></span>|  
|<span data-ttu-id="a04e4-474">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="a04e4-474">CHECK_OPTION</span></span>|<span data-ttu-id="a04e4-475">Boolean</span><span class="sxs-lookup"><span data-stu-id="a04e4-475">Boolean</span></span>|  
|<span data-ttu-id="a04e4-476">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="a04e4-476">IS_UPDATABLE</span></span>|<span data-ttu-id="a04e4-477">Boolean</span><span class="sxs-lookup"><span data-stu-id="a04e4-477">Boolean</span></span>|  
|<span data-ttu-id="a04e4-478">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a04e4-478">DESCRIPTION</span></span>|<span data-ttu-id="a04e4-479">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-479">String</span></span>|  
|<span data-ttu-id="a04e4-480">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="a04e4-480">DATE_CREATED</span></span>|<span data-ttu-id="a04e4-481">DateTime</span><span class="sxs-lookup"><span data-stu-id="a04e4-481">DateTime</span></span>|  
|<span data-ttu-id="a04e4-482">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="a04e4-482">DATE_MODIFIED</span></span>|<span data-ttu-id="a04e4-483">DateTime</span><span class="sxs-lookup"><span data-stu-id="a04e4-483">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="a04e4-484">Indexes</span><span class="sxs-lookup"><span data-stu-id="a04e4-484">Indexes</span></span>  
  
|<span data-ttu-id="a04e4-485">ColumnName</span><span class="sxs-lookup"><span data-stu-id="a04e4-485">ColumnName</span></span>|<span data-ttu-id="a04e4-486">DataType</span><span class="sxs-lookup"><span data-stu-id="a04e4-486">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="a04e4-487">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="a04e4-487">TABLE_CATALOG</span></span>|<span data-ttu-id="a04e4-488">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-488">String</span></span>|  
|<span data-ttu-id="a04e4-489">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="a04e4-489">TABLE_SCHEMA</span></span>|<span data-ttu-id="a04e4-490">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-490">String</span></span>|  
|<span data-ttu-id="a04e4-491">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="a04e4-491">TABLE_NAME</span></span>|<span data-ttu-id="a04e4-492">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-492">String</span></span>|  
|<span data-ttu-id="a04e4-493">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="a04e4-493">INDEX_CATALOG</span></span>|<span data-ttu-id="a04e4-494">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-494">String</span></span>|  
|<span data-ttu-id="a04e4-495">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="a04e4-495">INDEX_SCHEMA</span></span>|<span data-ttu-id="a04e4-496">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-496">String</span></span>|  
|<span data-ttu-id="a04e4-497">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="a04e4-497">INDEX_NAME</span></span>|<span data-ttu-id="a04e4-498">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-498">String</span></span>|  
|<span data-ttu-id="a04e4-499">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="a04e4-499">PRIMARY_KEY</span></span>|<span data-ttu-id="a04e4-500">Boolean</span><span class="sxs-lookup"><span data-stu-id="a04e4-500">Boolean</span></span>|  
|<span data-ttu-id="a04e4-501">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="a04e4-501">UNIQUE</span></span>|<span data-ttu-id="a04e4-502">Boolean</span><span class="sxs-lookup"><span data-stu-id="a04e4-502">Boolean</span></span>|  
|<span data-ttu-id="a04e4-503">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="a04e4-503">CLUSTERED</span></span>|<span data-ttu-id="a04e4-504">Boolean</span><span class="sxs-lookup"><span data-stu-id="a04e4-504">Boolean</span></span>|  
|<span data-ttu-id="a04e4-505">TYPE</span><span class="sxs-lookup"><span data-stu-id="a04e4-505">TYPE</span></span>|<span data-ttu-id="a04e4-506">Int32</span><span class="sxs-lookup"><span data-stu-id="a04e4-506">Int32</span></span>|  
|<span data-ttu-id="a04e4-507">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="a04e4-507">FILL_FACTOR</span></span>|<span data-ttu-id="a04e4-508">Int32</span><span class="sxs-lookup"><span data-stu-id="a04e4-508">Int32</span></span>|  
|<span data-ttu-id="a04e4-509">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="a04e4-509">INITIAL_SIZE</span></span>|<span data-ttu-id="a04e4-510">Int32</span><span class="sxs-lookup"><span data-stu-id="a04e4-510">Int32</span></span>|  
|<span data-ttu-id="a04e4-511">NULLS</span><span class="sxs-lookup"><span data-stu-id="a04e4-511">NULLS</span></span>|<span data-ttu-id="a04e4-512">Int32</span><span class="sxs-lookup"><span data-stu-id="a04e4-512">Int32</span></span>|  
|<span data-ttu-id="a04e4-513">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="a04e4-513">SORT_BOOKMARKS</span></span>|<span data-ttu-id="a04e4-514">Boolean</span><span class="sxs-lookup"><span data-stu-id="a04e4-514">Boolean</span></span>|  
|<span data-ttu-id="a04e4-515">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="a04e4-515">AUTO_UPDATE</span></span>|<span data-ttu-id="a04e4-516">Boolean</span><span class="sxs-lookup"><span data-stu-id="a04e4-516">Boolean</span></span>|  
|<span data-ttu-id="a04e4-517">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="a04e4-517">NULL_COLLATION</span></span>|<span data-ttu-id="a04e4-518">Int32</span><span class="sxs-lookup"><span data-stu-id="a04e4-518">Int32</span></span>|  
|<span data-ttu-id="a04e4-519">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="a04e4-519">ORDINAL_POSITION</span></span>|<span data-ttu-id="a04e4-520">Int64</span><span class="sxs-lookup"><span data-stu-id="a04e4-520">Int64</span></span>|  
|<span data-ttu-id="a04e4-521">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="a04e4-521">COLUMN_NAME</span></span>|<span data-ttu-id="a04e4-522">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-522">String</span></span>|  
|<span data-ttu-id="a04e4-523">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="a04e4-523">COLUMN_GUID</span></span>|<span data-ttu-id="a04e4-524">Guid</span><span class="sxs-lookup"><span data-stu-id="a04e4-524">Guid</span></span>|  
|<span data-ttu-id="a04e4-525">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="a04e4-525">COLUMN_PROPID</span></span>|<span data-ttu-id="a04e4-526">Int64</span><span class="sxs-lookup"><span data-stu-id="a04e4-526">Int64</span></span>|  
|<span data-ttu-id="a04e4-527">COLLATION</span><span class="sxs-lookup"><span data-stu-id="a04e4-527">COLLATION</span></span>|<span data-ttu-id="a04e4-528">Int16</span><span class="sxs-lookup"><span data-stu-id="a04e4-528">Int16</span></span>|  
|<span data-ttu-id="a04e4-529">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="a04e4-529">CARDINALITY</span></span>|<span data-ttu-id="a04e4-530">Десятичное число</span><span class="sxs-lookup"><span data-stu-id="a04e4-530">Decimal</span></span>|  
|<span data-ttu-id="a04e4-531">PAGES</span><span class="sxs-lookup"><span data-stu-id="a04e4-531">PAGES</span></span>|<span data-ttu-id="a04e4-532">Int32</span><span class="sxs-lookup"><span data-stu-id="a04e4-532">Int32</span></span>|  
|<span data-ttu-id="a04e4-533">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="a04e4-533">FILTER_CONDITION</span></span>|<span data-ttu-id="a04e4-534">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-534">String</span></span>|  
|<span data-ttu-id="a04e4-535">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="a04e4-535">INTEGRATED</span></span>|<span data-ttu-id="a04e4-536">Boolean</span><span class="sxs-lookup"><span data-stu-id="a04e4-536">Boolean</span></span>|  
  
## <a name="microsoft-jet-ole-db-provider"></a><span data-ttu-id="a04e4-537">Поставщик OLE DB для Microsoft Jet</span><span class="sxs-lookup"><span data-stu-id="a04e4-537">Microsoft Jet OLE DB Provider</span></span>  
 <span data-ttu-id="a04e4-538">Драйвер OLE DB для Jet (Майкрософт) поддерживает следующие специальные коллекции схем в дополнение к общим коллекциям.</span><span class="sxs-lookup"><span data-stu-id="a04e4-538">The Microsoft Jet OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="a04e4-539">Таблицы</span><span class="sxs-lookup"><span data-stu-id="a04e4-539">Tables</span></span>  
  
-   <span data-ttu-id="a04e4-540">Столбцы</span><span class="sxs-lookup"><span data-stu-id="a04e4-540">Columns</span></span>  
  
-   <span data-ttu-id="a04e4-541">Процедуры</span><span class="sxs-lookup"><span data-stu-id="a04e4-541">Procedures</span></span>  
  
-   <span data-ttu-id="a04e4-542">Представления</span><span class="sxs-lookup"><span data-stu-id="a04e4-542">Views</span></span>  
  
-   <span data-ttu-id="a04e4-543">Indexes</span><span class="sxs-lookup"><span data-stu-id="a04e4-543">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="a04e4-544">Таблицы</span><span class="sxs-lookup"><span data-stu-id="a04e4-544">Tables</span></span>  
  
|<span data-ttu-id="a04e4-545">ColumnName</span><span class="sxs-lookup"><span data-stu-id="a04e4-545">ColumnName</span></span>|<span data-ttu-id="a04e4-546">DataType</span><span class="sxs-lookup"><span data-stu-id="a04e4-546">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="a04e4-547">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="a04e4-547">TABLE_CATALOG</span></span>|<span data-ttu-id="a04e4-548">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-548">String</span></span>|  
|<span data-ttu-id="a04e4-549">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="a04e4-549">TABLE_SCHEMA</span></span>|<span data-ttu-id="a04e4-550">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-550">String</span></span>|  
|<span data-ttu-id="a04e4-551">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="a04e4-551">TABLE_NAME</span></span>|<span data-ttu-id="a04e4-552">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-552">String</span></span>|  
|<span data-ttu-id="a04e4-553">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="a04e4-553">TABLE_TYPE</span></span>|<span data-ttu-id="a04e4-554">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-554">String</span></span>|  
|<span data-ttu-id="a04e4-555">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="a04e4-555">TABLE_GUID</span></span>|<span data-ttu-id="a04e4-556">Guid</span><span class="sxs-lookup"><span data-stu-id="a04e4-556">Guid</span></span>|  
|<span data-ttu-id="a04e4-557">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a04e4-557">DESCRIPTION</span></span>|<span data-ttu-id="a04e4-558">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-558">String</span></span>|  
|<span data-ttu-id="a04e4-559">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="a04e4-559">TABLE_PROPID</span></span>|<span data-ttu-id="a04e4-560">Int64</span><span class="sxs-lookup"><span data-stu-id="a04e4-560">Int64</span></span>|  
|<span data-ttu-id="a04e4-561">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="a04e4-561">DATE_CREATED</span></span>|<span data-ttu-id="a04e4-562">DateTime</span><span class="sxs-lookup"><span data-stu-id="a04e4-562">DateTime</span></span>|  
|<span data-ttu-id="a04e4-563">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="a04e4-563">DATE_MODIFIED</span></span>|<span data-ttu-id="a04e4-564">DateTime</span><span class="sxs-lookup"><span data-stu-id="a04e4-564">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="a04e4-565">Столбцы</span><span class="sxs-lookup"><span data-stu-id="a04e4-565">Columns</span></span>  
  
|<span data-ttu-id="a04e4-566">ColumnName</span><span class="sxs-lookup"><span data-stu-id="a04e4-566">ColumnName</span></span>|<span data-ttu-id="a04e4-567">DataType</span><span class="sxs-lookup"><span data-stu-id="a04e4-567">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="a04e4-568">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="a04e4-568">TABLE_CATALOG</span></span>|<span data-ttu-id="a04e4-569">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-569">String</span></span>|  
|<span data-ttu-id="a04e4-570">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="a04e4-570">TABLE_SCHEMA</span></span>|<span data-ttu-id="a04e4-571">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-571">String</span></span>|  
|<span data-ttu-id="a04e4-572">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="a04e4-572">TABLE_NAME</span></span>|<span data-ttu-id="a04e4-573">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-573">String</span></span>|  
|<span data-ttu-id="a04e4-574">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="a04e4-574">COLUMN_NAME</span></span>|<span data-ttu-id="a04e4-575">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-575">String</span></span>|  
|<span data-ttu-id="a04e4-576">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="a04e4-576">COLUMN_GUID</span></span>|<span data-ttu-id="a04e4-577">Guid</span><span class="sxs-lookup"><span data-stu-id="a04e4-577">Guid</span></span>|  
|<span data-ttu-id="a04e4-578">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="a04e4-578">COLUMN_PROPID</span></span>|<span data-ttu-id="a04e4-579">Int64</span><span class="sxs-lookup"><span data-stu-id="a04e4-579">Int64</span></span>|  
|<span data-ttu-id="a04e4-580">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="a04e4-580">ORDINAL_POSITION</span></span>|<span data-ttu-id="a04e4-581">Int64</span><span class="sxs-lookup"><span data-stu-id="a04e4-581">Int64</span></span>|  
|<span data-ttu-id="a04e4-582">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="a04e4-582">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="a04e4-583">Boolean</span><span class="sxs-lookup"><span data-stu-id="a04e4-583">Boolean</span></span>|  
|<span data-ttu-id="a04e4-584">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="a04e4-584">COLUMN_DEFAULT</span></span>|<span data-ttu-id="a04e4-585">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-585">String</span></span>|  
|<span data-ttu-id="a04e4-586">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="a04e4-586">COLUMN_FLAGS</span></span>|<span data-ttu-id="a04e4-587">Int64</span><span class="sxs-lookup"><span data-stu-id="a04e4-587">Int64</span></span>|  
|<span data-ttu-id="a04e4-588">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="a04e4-588">IS_NULLABLE</span></span>|<span data-ttu-id="a04e4-589">Boolean</span><span class="sxs-lookup"><span data-stu-id="a04e4-589">Boolean</span></span>|  
|<span data-ttu-id="a04e4-590">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="a04e4-590">DATA_TYPE</span></span>|<span data-ttu-id="a04e4-591">Int32</span><span class="sxs-lookup"><span data-stu-id="a04e4-591">Int32</span></span>|  
|<span data-ttu-id="a04e4-592">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="a04e4-592">TYPE_GUID</span></span>|<span data-ttu-id="a04e4-593">Guid</span><span class="sxs-lookup"><span data-stu-id="a04e4-593">Guid</span></span>|  
|<span data-ttu-id="a04e4-594">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="a04e4-594">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="a04e4-595">Int64</span><span class="sxs-lookup"><span data-stu-id="a04e4-595">Int64</span></span>|  
|<span data-ttu-id="a04e4-596">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="a04e4-596">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="a04e4-597">Int64</span><span class="sxs-lookup"><span data-stu-id="a04e4-597">Int64</span></span>|  
|<span data-ttu-id="a04e4-598">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="a04e4-598">NUMERIC_PRECISION</span></span>|<span data-ttu-id="a04e4-599">Int32</span><span class="sxs-lookup"><span data-stu-id="a04e4-599">Int32</span></span>|  
|<span data-ttu-id="a04e4-600">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="a04e4-600">NUMERIC_SCALE</span></span>|<span data-ttu-id="a04e4-601">Int16</span><span class="sxs-lookup"><span data-stu-id="a04e4-601">Int16</span></span>|  
|<span data-ttu-id="a04e4-602">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="a04e4-602">DATETIME_PRECISION</span></span>|<span data-ttu-id="a04e4-603">Int64</span><span class="sxs-lookup"><span data-stu-id="a04e4-603">Int64</span></span>|  
|<span data-ttu-id="a04e4-604">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="a04e4-604">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="a04e4-605">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-605">String</span></span>|  
|<span data-ttu-id="a04e4-606">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="a04e4-606">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="a04e4-607">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-607">String</span></span>|  
|<span data-ttu-id="a04e4-608">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="a04e4-608">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="a04e4-609">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-609">String</span></span>|  
|<span data-ttu-id="a04e4-610">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="a04e4-610">COLLATION_CATALOG</span></span>|<span data-ttu-id="a04e4-611">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-611">String</span></span>|  
|<span data-ttu-id="a04e4-612">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="a04e4-612">COLLATION_SCHEMA</span></span>|<span data-ttu-id="a04e4-613">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-613">String</span></span>|  
|<span data-ttu-id="a04e4-614">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="a04e4-614">COLLATION_NAME</span></span>|<span data-ttu-id="a04e4-615">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-615">String</span></span>|  
|<span data-ttu-id="a04e4-616">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="a04e4-616">DOMAIN_CATALOG</span></span>|<span data-ttu-id="a04e4-617">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-617">String</span></span>|  
|<span data-ttu-id="a04e4-618">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="a04e4-618">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="a04e4-619">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-619">String</span></span>|  
|<span data-ttu-id="a04e4-620">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="a04e4-620">DOMAIN_NAME</span></span>|<span data-ttu-id="a04e4-621">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-621">String</span></span>|  
|<span data-ttu-id="a04e4-622">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a04e4-622">DESCRIPTION</span></span>|<span data-ttu-id="a04e4-623">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-623">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="a04e4-624">Процедуры</span><span class="sxs-lookup"><span data-stu-id="a04e4-624">Procedures</span></span>  
  
|<span data-ttu-id="a04e4-625">ColumnName</span><span class="sxs-lookup"><span data-stu-id="a04e4-625">ColumnName</span></span>|<span data-ttu-id="a04e4-626">DataType</span><span class="sxs-lookup"><span data-stu-id="a04e4-626">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="a04e4-627">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="a04e4-627">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="a04e4-628">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-628">String</span></span>|  
|<span data-ttu-id="a04e4-629">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="a04e4-629">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="a04e4-630">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-630">String</span></span>|  
|<span data-ttu-id="a04e4-631">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="a04e4-631">PROCEDURE_NAME</span></span>|<span data-ttu-id="a04e4-632">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-632">String</span></span>|  
|<span data-ttu-id="a04e4-633">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="a04e4-633">PROCEDURE_TYPE</span></span>|<span data-ttu-id="a04e4-634">Int16</span><span class="sxs-lookup"><span data-stu-id="a04e4-634">Int16</span></span>|  
|<span data-ttu-id="a04e4-635">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="a04e4-635">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="a04e4-636">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-636">String</span></span>|  
|<span data-ttu-id="a04e4-637">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a04e4-637">DESCRIPTION</span></span>|<span data-ttu-id="a04e4-638">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-638">String</span></span>|  
|<span data-ttu-id="a04e4-639">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="a04e4-639">DATE_CREATED</span></span>|<span data-ttu-id="a04e4-640">DateTime</span><span class="sxs-lookup"><span data-stu-id="a04e4-640">DateTime</span></span>|  
|<span data-ttu-id="a04e4-641">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="a04e4-641">DATE_MODIFIED</span></span>|<span data-ttu-id="a04e4-642">DateTime</span><span class="sxs-lookup"><span data-stu-id="a04e4-642">DateTime</span></span>|  
  
### <a name="views"></a><span data-ttu-id="a04e4-643">Представления</span><span class="sxs-lookup"><span data-stu-id="a04e4-643">Views</span></span>  
  
|<span data-ttu-id="a04e4-644">ColumnName</span><span class="sxs-lookup"><span data-stu-id="a04e4-644">ColumnName</span></span>|<span data-ttu-id="a04e4-645">DataType</span><span class="sxs-lookup"><span data-stu-id="a04e4-645">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="a04e4-646">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="a04e4-646">TABLE_CATALOG</span></span>|<span data-ttu-id="a04e4-647">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-647">String</span></span>|  
|<span data-ttu-id="a04e4-648">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="a04e4-648">TABLE_SCHEMA</span></span>|<span data-ttu-id="a04e4-649">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-649">String</span></span>|  
|<span data-ttu-id="a04e4-650">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="a04e4-650">TABLE_NAME</span></span>|<span data-ttu-id="a04e4-651">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-651">String</span></span>|  
|<span data-ttu-id="a04e4-652">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="a04e4-652">VIEW_DEFINITION</span></span>|<span data-ttu-id="a04e4-653">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-653">String</span></span>|  
|<span data-ttu-id="a04e4-654">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="a04e4-654">CHECK_OPTION</span></span>|<span data-ttu-id="a04e4-655">Boolean</span><span class="sxs-lookup"><span data-stu-id="a04e4-655">Boolean</span></span>|  
|<span data-ttu-id="a04e4-656">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="a04e4-656">IS_UPDATABLE</span></span>|<span data-ttu-id="a04e4-657">Boolean</span><span class="sxs-lookup"><span data-stu-id="a04e4-657">Boolean</span></span>|  
|<span data-ttu-id="a04e4-658">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a04e4-658">DESCRIPTION</span></span>|<span data-ttu-id="a04e4-659">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-659">String</span></span>|  
|<span data-ttu-id="a04e4-660">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="a04e4-660">DATE_CREATED</span></span>|<span data-ttu-id="a04e4-661">DateTime</span><span class="sxs-lookup"><span data-stu-id="a04e4-661">DateTime</span></span>|  
|<span data-ttu-id="a04e4-662">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="a04e4-662">DATE_MODIFIED</span></span>|<span data-ttu-id="a04e4-663">DateTime</span><span class="sxs-lookup"><span data-stu-id="a04e4-663">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="a04e4-664">Indexes</span><span class="sxs-lookup"><span data-stu-id="a04e4-664">Indexes</span></span>  
  
|<span data-ttu-id="a04e4-665">ColumnName</span><span class="sxs-lookup"><span data-stu-id="a04e4-665">ColumnName</span></span>|<span data-ttu-id="a04e4-666">DataType</span><span class="sxs-lookup"><span data-stu-id="a04e4-666">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="a04e4-667">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="a04e4-667">TABLE_CATALOG</span></span>|<span data-ttu-id="a04e4-668">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-668">String</span></span>|  
|<span data-ttu-id="a04e4-669">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="a04e4-669">TABLE_SCHEMA</span></span>|<span data-ttu-id="a04e4-670">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-670">String</span></span>|  
|<span data-ttu-id="a04e4-671">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="a04e4-671">TABLE_NAME</span></span>|<span data-ttu-id="a04e4-672">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-672">String</span></span>|  
|<span data-ttu-id="a04e4-673">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="a04e4-673">INDEX_CATALOG</span></span>|<span data-ttu-id="a04e4-674">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-674">String</span></span>|  
|<span data-ttu-id="a04e4-675">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="a04e4-675">INDEX_SCHEMA</span></span>|<span data-ttu-id="a04e4-676">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-676">String</span></span>|  
|<span data-ttu-id="a04e4-677">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="a04e4-677">INDEX_NAME</span></span>|<span data-ttu-id="a04e4-678">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-678">String</span></span>|  
|<span data-ttu-id="a04e4-679">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="a04e4-679">PRIMARY_KEY</span></span>|<span data-ttu-id="a04e4-680">Boolean</span><span class="sxs-lookup"><span data-stu-id="a04e4-680">Boolean</span></span>|  
|<span data-ttu-id="a04e4-681">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="a04e4-681">UNIQUE</span></span>|<span data-ttu-id="a04e4-682">Boolean</span><span class="sxs-lookup"><span data-stu-id="a04e4-682">Boolean</span></span>|  
|<span data-ttu-id="a04e4-683">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="a04e4-683">CLUSTERED</span></span>|<span data-ttu-id="a04e4-684">Boolean</span><span class="sxs-lookup"><span data-stu-id="a04e4-684">Boolean</span></span>|  
|<span data-ttu-id="a04e4-685">TYPE</span><span class="sxs-lookup"><span data-stu-id="a04e4-685">TYPE</span></span>|<span data-ttu-id="a04e4-686">Int32</span><span class="sxs-lookup"><span data-stu-id="a04e4-686">Int32</span></span>|  
|<span data-ttu-id="a04e4-687">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="a04e4-687">FILL_FACTOR</span></span>|<span data-ttu-id="a04e4-688">Int32</span><span class="sxs-lookup"><span data-stu-id="a04e4-688">Int32</span></span>|  
|<span data-ttu-id="a04e4-689">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="a04e4-689">INITIAL_SIZE</span></span>|<span data-ttu-id="a04e4-690">Int32</span><span class="sxs-lookup"><span data-stu-id="a04e4-690">Int32</span></span>|  
|<span data-ttu-id="a04e4-691">NULLS</span><span class="sxs-lookup"><span data-stu-id="a04e4-691">NULLS</span></span>|<span data-ttu-id="a04e4-692">Int32</span><span class="sxs-lookup"><span data-stu-id="a04e4-692">Int32</span></span>|  
|<span data-ttu-id="a04e4-693">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="a04e4-693">SORT_BOOKMARKS</span></span>|<span data-ttu-id="a04e4-694">Boolean</span><span class="sxs-lookup"><span data-stu-id="a04e4-694">Boolean</span></span>|  
|<span data-ttu-id="a04e4-695">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="a04e4-695">AUTO_UPDATE</span></span>|<span data-ttu-id="a04e4-696">Boolean</span><span class="sxs-lookup"><span data-stu-id="a04e4-696">Boolean</span></span>|  
|<span data-ttu-id="a04e4-697">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="a04e4-697">NULL_COLLATION</span></span>|<span data-ttu-id="a04e4-698">Int32</span><span class="sxs-lookup"><span data-stu-id="a04e4-698">Int32</span></span>|  
|<span data-ttu-id="a04e4-699">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="a04e4-699">ORDINAL_POSITION</span></span>|<span data-ttu-id="a04e4-700">Int64</span><span class="sxs-lookup"><span data-stu-id="a04e4-700">Int64</span></span>|  
|<span data-ttu-id="a04e4-701">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="a04e4-701">COLUMN_NAME</span></span>|<span data-ttu-id="a04e4-702">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-702">String</span></span>|  
|<span data-ttu-id="a04e4-703">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="a04e4-703">COLUMN_GUID</span></span>|<span data-ttu-id="a04e4-704">Guid</span><span class="sxs-lookup"><span data-stu-id="a04e4-704">Guid</span></span>|  
|<span data-ttu-id="a04e4-705">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="a04e4-705">COLUMN_PROPID</span></span>|<span data-ttu-id="a04e4-706">Int64</span><span class="sxs-lookup"><span data-stu-id="a04e4-706">Int64</span></span>|  
|<span data-ttu-id="a04e4-707">COLLATION</span><span class="sxs-lookup"><span data-stu-id="a04e4-707">COLLATION</span></span>|<span data-ttu-id="a04e4-708">Int16</span><span class="sxs-lookup"><span data-stu-id="a04e4-708">Int16</span></span>|  
|<span data-ttu-id="a04e4-709">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="a04e4-709">CARDINALITY</span></span>|<span data-ttu-id="a04e4-710">Десятичное число</span><span class="sxs-lookup"><span data-stu-id="a04e4-710">Decimal</span></span>|  
|<span data-ttu-id="a04e4-711">PAGES</span><span class="sxs-lookup"><span data-stu-id="a04e4-711">PAGES</span></span>|<span data-ttu-id="a04e4-712">Int32</span><span class="sxs-lookup"><span data-stu-id="a04e4-712">Int32</span></span>|  
|<span data-ttu-id="a04e4-713">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="a04e4-713">FILTER_CONDITION</span></span>|<span data-ttu-id="a04e4-714">Строковое</span><span class="sxs-lookup"><span data-stu-id="a04e4-714">String</span></span>|  
|<span data-ttu-id="a04e4-715">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="a04e4-715">INTEGRATED</span></span>|<span data-ttu-id="a04e4-716">Boolean</span><span class="sxs-lookup"><span data-stu-id="a04e4-716">Boolean</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a04e4-717">См. также</span><span class="sxs-lookup"><span data-stu-id="a04e4-717">See Also</span></span>  
 [<span data-ttu-id="a04e4-718">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a04e4-718">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
