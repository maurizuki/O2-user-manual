---
title: Relations
nav_order: 7
---

# Relations
{: .no_toc }

A relation connects two objects and gives each of them a role. Use relations to record who is married to whom, which company a person works for, which credit card belongs to which bank account, and so on.

1. TOC
{:toc}

---

## Create a relation

1. In the objects list, select exactly two objects (click the first, then **Ctrl+click** the second).
2. Choose **New relation** from the **New** menu or the object menu.
3. In the **Relation properties** dialog, *Object 1* and *Object 2* show the two objects. Fill in:
   - **Role 1**: the role of object 1, for example `husband`.
   - **Role 2**: the role of object 2, for example `wife`.

   Both boxes suggest roles already used in the file.
4. Click **OK**.

Roles are optional, but they make the **Relations** tab much easier to read.

### Role examples

| Object 1 | Role 1 | Object 2 | Role 2 |
|:---------|:-------|:---------|:-------|
| Frank | husband | Pamela | wife |
| Contoso Ltd. | employer | Garrett | employee |
| Vanessa | sister | Frank Jr. | brother |
| Checking account | account | Visa card | linked card |

## View relations

Select an object and open the **Relations** tab. It lists every object related to the selected one, with the other object's **Role**.

- **Ctrl+click** a relation, or choose **Go to object** from its menu, to select the other object in the list.
- **Double-click** a relation, or press **Enter**, to edit it.

## Edit or delete a relation

Right-click a relation on the **Relations** tab:

- **Properties** changes the roles.
- **Delete** removes the relation after confirmation. The two objects are not affected.

Deleting an object also deletes all its relations.

## Rename a role everywhere

To rename a role in many relations at once, select the objects whose relations you want to change and choose **Replace role** from the object menu. See [Bulk changes]({% link docs/objects.md %}#bulk-changes).
