# Npm link

The `npm link` command allows you to link 2 repositories that are dependant on each other.

For example, if you are working on forms and one of your repository handles the form itself while another repository handles the validation rules, you can link them together so the changes made to your validations will be reflected on your form UI.

You have to figure out which repository is dependant on the other one. In our example of form and validation rules, the form UI is dependant on the rules, but the rules themselves don't care about the form, so the main command will have to be run from the form repo.

To do so, cd into your form repository and run the following command:

```
npm link <the name of your npm package>
# You can find the name in the package.json file, it is usually the first line.
```

Then, cd into the node module you indicated before and run:

```
npm link
```

This will create a symlink between the 2 repositories and the updates made to one will work with the other one without having to publish the npm package each time.
