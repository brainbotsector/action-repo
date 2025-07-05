# action-repo

Repository configured to trigger webhook events on GitHub actions (push, pull request, merge) to a specified endpoint.

## Configuration

Set up webhook:

Go to: Settings → Webhooks → Add webhook

Payload URL: https://your-webhook-url/webhook

Content type: application/json

Events: Select "Let me select individual events" and choose:

    -Push

    -Pull request

    -Merge

Using ngrok for local testing:

```bash
ngrok http 5000
```

Use the generated HTTPS URL as your webhook endpoint

## Testing Events

Push Event
```bash
echo "Test content" >> test.txt
git add .
git commit -m "Test push"
git push origin main
```

Pull Request

```bash
git checkout -b test-branch
echo "PR content" >> pr.txt
git add .
git commit -m "PR test"
git push origin test-branch
```

# Then create Pull Request via GitHub

Merge Event

Create PR via GitHub 

Click "Merge pull request"
