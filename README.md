<div align="center">
<h2>helPR</h2>
</div>

A GitHub App built with [Probot](https://github.com/probot/probot) that assigns labels to issues based on the status of the PR associated with it.

## Usage

Using helpr is pretty straightforward. Just [install](https://github.com/apps/helpr) the app on your repository and you are ready to go. :100: 


Consider this open issue :

![issue](./screenshots/usage-img2.jpg)
<br><br>

Now when someone references this issue in a pull request helpr will automatically add the label `pr-available` :

![labelled](./screenshots/usage-img1.jpg)
<br><br>


**helpr** supports 3 labels :
* `pr-available` when  a new PR referencing an issue is opened.
* `pr-merged` when a PR referencing an issue is merged.
* `pr-rejected` when a PR referencing an issue is rejected.

When a PR for an issue is merged or rejected **helpr** will remove the `pr-available` label and add the respective merged or rejected label.

## Configuring

You can choose label names as per your liking :smile:

Add a `helpr` object in your `.github/config.yml` file (and make the file if you don't already have it) like this:

```yaml
helpr:
  opened: 'insert-label-for-pr-opened-here'
  merged: 'insert-label-for-pr-merged-here'
  rejected: 'insert-label-for-pr-rejected-here'
```  

Only override the ones that you want to change!

The defaults are:
```yaml
opened: 'pr-available'
merged: 'pr-merged'
rejected: 'pr-rejected'
```

## Setup

```sh
# Install dependencies
npm install

# Run the bot
npm start
```

See [docs/deploy.md](docs/deploy.md) if you would like to run your own instance of this app.
