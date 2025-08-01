const stripe = require('stripe')(process.env.STRIPE_SECRET);

app.post('/api/create-checkout-session', async (req, res) => {
  const session = await stripe.checkout.sessions.create({
    payment_method_types: ['card'],
    line_items: req.body.items,
    mode: 'payment',
    success_url: 'http://localhost:3000/success',
    cancel_url: 'http://localhost:3000/cancel',
  });
  res.json({ url: session.url });
});
{
  username: String,
  email: String,
  password: String (hashed),
  projects: [projectId]
}
{
  name: String,
  description: String,
  members: [userId],
  tasks: [taskId]
}
{
  title: String,
  description: String,
  assignedTo: userId,
  status: "Todo" | "In Progress" | "Done",
  deadline: Date,
  projectId: projectId
}
