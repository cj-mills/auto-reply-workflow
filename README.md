# Auto-reply to new issues

This GitHub action automatically posts a custom comment on new issues created in your repository. By default, it will post a message thanking the user for creating the issue and indicating that the issues are typically addressed on Thursdays.

## Usage

To use this action in your repository, create a new workflow in your `.github/workflows` directory, for example: `auto_reply.yml`.

Add the following content to your workflow file:

```yaml
name: Auto-reply to new issues

on:
  issues:
    types: [opened]

jobs:
  auto_reply:
    runs-on: ubuntu-latest
    steps:
    - name: Auto-reply to new issues
      uses: cj-mills/auto-reply-workflow@main
```



You can also customize the `issue-comment` input to set your desired auto-reply message.



## Inputs

### `issue-comment` (required)

The comment to post on the new issue. The default message is:

```text
Thank you for creating an issue! I typically address new issues on Thursdays. I'll get back to you as soon as I can. :clock1:
```



## Example

```yaml
name: Auto-reply to new issues

on:
  issues:
    types: [opened]

jobs:
  auto_reply:
    runs-on: ubuntu-latest
    steps:
    - name: Auto-reply to new issues
      uses: cj-mills/auto-reply-workflow@main
       with:
         issue-comment: "Thank you for your issue! Our team will review it and get back to you shortly."
```



## Permissions

To use this action in your repository, you need to enable the "Read and write permissions" option for the Actions feature. This can be done in your repository settings. Follow these steps:

1. Go to the main page of your GitHub repository.
2. Click on the "Settings" tab.
3. In the left sidebar, click on "Actions".
4. Under "General" section, locate the "Workflow permissions" heading.
5. Select the "Read and write permissions" option.

After enabling the required permissions, you can proceed with creating and configuring the workflow as described in the "Usage" section.

Make sure to enable the "Read and write permissions" for each repository you want to add this workflow to.





## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

















