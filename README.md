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
