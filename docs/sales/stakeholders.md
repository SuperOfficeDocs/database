---
# This basic template provides core metadata fields for Markdown articles on docs.superoffice.com.

# Mandatory fields.
title: sale_stakeholders       # (Required) Very important for SEO. Intent in a unique string of 43-59 chars including spaces.
description: Sale stakeholders # (Required) Important for SEO. Recommended character length is 115-145 characters including spaces.
author: {github-id}             # Your GitHub alias.
keywords: database
so.topic: concept              # article, howto, reference, concept, guide

# Optional fields. Don't forget to remove # if you need a field.
# so.envir:                     # cloud or onsite
# so.client:                    # online, web, win, pocket, or mobile
---

# Sale stakeholders

New from 7.1: A sale may now have one or more stakeholders, a contact or person with an extra interest or role in the sale. This may be turned off using the preference in **SOAdmin - Preferences - Sale - Enable Stakeholders (default yes)**

With this preference turned on a new archive is presented for sales of type

![Stakeholders][img1]

This will also make the sale visible on more than one company salesarchive if **Include Stakeholders** is ticket.

![Include Stakeholders][img2]

Use your favorite query tool and try this query:

```sql
SELECT * FROM saletype where hasStakeholders = 1
```

If there are sales defined which may have stakeholders, you may search the database for these sales:

```sql
SELECT * FROM sale where saletype_id in (select saletype_id from saletype where hasStakeholders = 1)
```

For these sales we may look up the stakeholders, this will present the stakeholders for sale_id = 4

```sql
SELECT * FROM salestakeholder where sale_id = 4
```

![SaleStakeholder table][img3]

<!-- Referenced images -->
[img1]: media/stakeholders.png
[img2]: media/include-stakeholders.png
[img3]: media/salestakeholder-table.png