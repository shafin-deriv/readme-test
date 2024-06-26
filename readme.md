## Syncing a Folder of Markdown Docs to ReadMe

The Markdown files will require YAML front matter with certain ReadMe documentation attributes. Check out our docs for more info on setting up your front matter.

Passing in a path to a directory will also sync any Markdown files that are located in subdirectories.
```
rdme docs path-to-markdown-files --version={project-version}
```
This command also has a dry run mode, which can be useful for initial setup and debugging. You can read more about dry run mode in our docs.

## Cleanup
If you wish to delete documents from ReadMe that are no longer present in your local directory, pass the --cleanup option to the command.

## Edit a Single ReadMe Doc on Your Local Machine
```
rdme docs:edit <slug> --version={project-version}
```

## Syncing a Single Markdown File to ReadMe
```
rdme docs:single path-to-markdown-file --version={project-version}
```
