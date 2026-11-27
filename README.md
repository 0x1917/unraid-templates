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

| Template                             | Image                            | Notes                                                                                                                                                                                  |
| ------------------------------------ | -------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `templates/my-opengym.xml`           | `0x1917/opengym:latest`          | Workout and body-weight tracker ([OpenGym](https://github.com/DuarteSantos8/openGym)).                                                                                                 |
| `templates/my-deepseek-harness.xml`  | `0x1917/deepseek-harness:latest` | An open-source agent harness developed by DeepSeek AI ([DSH](https://github.com/deepseek-ai/deepseek-harness)).                                                                        |
| `templates/my-magnitude.xml`         | `magnitudedev/magnitude:latest`  | Local LLM inference engine with OpenAI- and Anthropic-compatible APIs ([Magnitude](https://github.com/magnitudedev/magnitude)).                                                        |
| `templates/my-maya-inkling-mini.xml` | `maya-inkling-mini:latest`       | Inkling 2 Mini on one 24 GB NVIDIA GPU, with OpenAI- and Anthropic-compatible APIs ([maya-inkling-mini](https://github.com/alesha-pro/maya-inkling-mini)). The image is built locally. |

### Install a template

If the template is already on the Unraid Community Applications catalog, then just search
for the template and install it through the CA plugin. Otherwise, it can be manually installed:

1. On Unraid, copy the XML file into `/boot/config/plugins/dockerMan/templates-user/`
2. Open the Docker tab
3. Click **Add Container** 
4. Select the template from the drop-down menu
5. Fill in any required arguments
6. Click **Apply**
