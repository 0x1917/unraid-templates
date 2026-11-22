# unraid-templates

Container templates for Unraid.

One XML file in `templates/` adds one container to the Unraid Docker tab. The
file gives the image reference, the ports, the paths, the variables, and the
artwork that Unraid shows. See [Install a template](#install-a-template).

## Layout

```
templates/       one XML file for each container (my-<name>.xml)
assets/<name>/   each template's icon and screenshots, linked by raw URL
ca_profile.xml   the repository profile Community Applications shows
icon.png         the repository's icon in Community Applications
banner.png       the repository's social preview image on GitHub
```

Each template's artwork lives under `assets/<name>/`, and the XML links to it with a raw
GitHub URL.

## Templates

| Template                            | Image                            | Notes                                                                                                                                                                |
| ----------------------------------- | -------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `templates/my-opengym.xml`          | `0x1917/opengym:latest`          | Workout and body-weight tracker ([OpenGym](https://github.com/DuarteSantos8/openGym)).                                                                               |
| `templates/my-deepseek-harness.xml` | `0x1917/deepseek-harness:latest` | An [open-source](https://github.com/deepseek-ai/deepseek-harness) agent harness developed by DeepSeek AI.                                                            |
| `templates/my-postgres-shared.xml`  | `0x1917/postgres-shared:latest`  | [PostgreSQL](https://github.com/0x1917/postgres-shared) 17 with pgvector, VectorChord, PostGIS and pg_cron: one server for Immich, Dawarich, firecrawl and the rest. |

### Install a template

If the template is already on the Unraid Community Applications catalog, then just search
for the template and install it through the CA plugin. Otherwise, it can be manually installed:

1. On Unraid, copy the XML file into `/boot/config/plugins/dockerMan/templates-user/`
2. Open the Docker tab
3. Click **Add Container** 
4. Select the template from the drop-down menu
5. Fill in any required arguments
6. Click **Apply**
